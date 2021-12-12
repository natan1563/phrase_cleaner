<template>
  <div class="home">
    <div id="logoPhraseCleaner">
      <img src="@/assets/chat.svg" alt="">
      <h1>Phrase Cleaner</h1>
    </div>

    <div id="content">
      <h3 class="textBlue">Limpe Palavrões de suas frases ;)</h3>

      <div id="boxClean">
        <label 
          for="cleanSwearword"
          id="cleanedPhraseMensage"
          :class="phraseClean ? 'textGreen' : 'textBlue'"  
        >
          <p v-if="!phraseClean">Digite a sua frase</p>
          <p v-else>Frase limpinha :)</p>
        </label>

        <textarea 
          name="cleanSwearword" 
          id="cleanSwearword" 
          cols="35" 
          rows="5" 
          maxlength="255"
          :class="phraseClean ? 'borderGreen' : 'textContent'"
          v-model="textSwearword"
        ></textarea>

        <div id="characterCounter">
          <small>
            <span id="hotCharacter">{{ characterCounter }}</span>/255 caracteres
          </small>

          <small v-if="phraseClean">
            <span class="textGreen">4 palavrões</span> foram removidos
          </small>
        </div>
        
        <button 
          class="btnCleanPhrase backgroundBlue"
          v-if="!phraseClean"
          @click="cleanSwearword()"
        >
          Limpar frase
        </button>

        <button 
          v-else 
          class="btnCleanPhrase backgroundGreen"
          @click="cleanNewPhrase"
        >
          Limpar outra frase
        </button>
        
        <p id="copyright">Copyright &copy; 2021 - Todos os direitos reservados</p>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
  data() {
    return {
      characterCounter: 0,
      textSwearword: '',
      swearwordList: [
        'porra', 
        'merda',
        'corno',
        'puto'
      ],
      phraseClean: false
    }
  },
  watch: {
   textSwearword: function() {
     if (this.textSwearword.length > 255) {
       this.textSwearword = this.textSwearword.slice(0, 255)
     }

     this.characterCounter = this.textSwearword.length
   }
  },
  methods: {
    cleanSwearword() {    
      this.swearwordList.forEach(value => {
        if (this.textSwearword.match(value)) {
          this.textSwearword = this.textSwearword.replaceAll(value, '****')
        }
      })

      this.phraseClean = true
    },
    cleanNewPhrase() {
      this.phraseClean = false 
      this.textSwearword = ''
    }
  },
}
</script>

<style scoped>

  .home {
    display: flex;
    padding: 40px 10px;
    margin-top: 10vh;
    font-family: Arial, Helvetica, sans-serif;
  }
  
  button {
    cursor: pointer;
  }

  #logoPhraseCleaner {
    display: flex;
    color: #0945c7;
    font-size: 14px;
    font-weight: bold;
  }

  #logoPhraseCleaner img {
    width: 25px;
    height: 25px;
    margin-right: 5px;
    filter: invert(20%) sepia(50%) saturate(3508%) hue-rotate(210deg) brightness(105%) contrast(102%);
  }

  #content {
    margin: 100px 45px;
    max-width: 350px;
  }

  #hotCharacter {
    color: #f80303;
  }

  #boxClean {
    display: flex;
    flex-direction: column;
    font-size: 10px;
    font-family: Arial, Helvetica, sans-serif;
    margin-top: 25px;
  }

  #boxClean label,
  #cleanedPhraseMensage {
    font-size: 12px;
    font-weight: bold;
    margin-bottom: 7px;
  }
  
  .textContent {
    border: 1px solid #CCC;
  }

  #boxClean textarea {
    box-shadow: 0 2px 3px rgba(10, 10, 10, .1);
    font-size: 10px;
    font-family: Arial, Helvetica, sans-serif;
    color: rgb(73, 72, 72);
    padding: 7px;
    height: 60px;
  }

  .textBlue {
    color: #071d95;
  }

  .textGreen {
    color: #1adb44;
    font-weight: bold;
  }

  .backgroundBlue {
    background-color: #4176e9;
  }

  .borderGreen {
    border: 1px solid #1adb44;
  }

  .backgroundGreen {
    background: #1adb44;
  }

  #characterCounter {
    display: flex;
    flex-direction: row-reverse;
    justify-content: flex-start;
    justify-content: space-between;
  }

  #boxClean #characterCounter {
    text-align: right;
    margin-top: 5px;
    color: rgb(54, 54, 54);
  }

  .btnCleanPhrase {
    margin-top: 30px;
    border: none;
    color: #FFF;
    border-radius: 4px;
    padding: 7px 0;
    font-size: 12px;
  }

  #copyright {
    margin-top: 15px;
    text-align: center;
    color: #071d95;
    font-size: 8.5px;
  }
</style>
