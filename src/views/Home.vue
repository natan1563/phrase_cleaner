<template>
  <div class="home">
    <h1>Phrase Cleaner</h1>
    <h3>Limpe Palavrões de suas frases ;)</h3>

    <div id="boxClean">
      <label for="cleanSwearword">
        Digite a sua frase
      </label>

      <textarea name="cleanSwearword" id="cleanSwearword" cols="35" rows="5"></textarea>

      <small id="characterCounter">
        <span id="hotCharacter">178</span>/255 caracteres
      </small>
      <button id="btnCleanPhrase">Limpar frase</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  }
}
</script>

<style scoped>
  #hotCharacter {
    color: #f80303;
  }

  #boxClean {
    display: flex;
    flex-direction: column;
    max-width: 250px;
    font-size: 10px;
    font-family: Arial, Helvetica, sans-serif;
  }

  #boxClean #characterCounter {
    text-align: right;
    color: rgb(54, 54, 54);
  }

  #btnCleanPhrase {
    margin-top: 30px;
    border: none;
    color: #FFF;
    background: rgba(4, 0, 255, 0.87);
    border-radius: 4px;
    padding: 7px 0;
    font-size: 12px;
  }
</style>
