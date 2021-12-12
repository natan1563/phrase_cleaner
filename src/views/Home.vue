<template>
  <div class="home">
    <div id="logoPhraseCleaner">
      <img src="@/assets/chat.svg" alt="">
      <h1>Phrase Cleaner</h1>
    </div>

    <div id="content">
      <h3>Limpe Palavrões de suas frases ;)</h3>

      <div id="boxClean">
        <label for="cleanSwearword">
          Digite a sua frase
        </label>

        <textarea name="cleanSwearword" id="cleanSwearword" cols="35" rows="5" maxlength="255"></textarea>

        <small id="characterCounter">
          <span id="hotCharacter">178</span>/255 caracteres
        </small>
        <button id="btnCleanPhrase">Limpar frase</button>
        
        <p id="copyright">Copyright &copy; 2021 - Todos os direitos reservados</p>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
}
</script>

<style scoped>

  .home {
    display: flex;
    padding: 40px 10px;
    margin-top: 10vh;
    font-family: Arial, Helvetica, sans-serif;
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
  
  #content h3 {
    color: #071d95;
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

  #boxClean label {
    color: #071d95;
    font-size: 12px;
    font-weight: bold;
    margin-bottom: 7px;
  }

  #boxClean textarea {
    border: 1px solid #CCC;
    box-shadow: 0 2px 3px rgba(10, 10, 10, .1);
  }

  #boxClean #characterCounter {
    text-align: right;
    margin-top: 5px;
    color: rgb(54, 54, 54);
  }

  #btnCleanPhrase {
    margin-top: 30px;
    border: none;
    color: #FFF;
    background: #4176e9;
    border-radius: 4px;
    padding: 7px 0;
    font-size: 12px;
  }

  #copyright {
    margin-top: 15px;
    text-align: center;
    color: #071d95;
    font-size: 9px;
  }
</style>
