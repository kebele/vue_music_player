<template>
  <div id="app">
    <header>
      <h1>music player</h1>
    </header>
    <main>
      <section class="player">
        <h2 class="song-title">{{ current.title }}</h2>
      </section>
    </main>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      current : {
        title : 'SONG TITLE',

      }
    }
  }

}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
header {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 15px;
  background-color: coral;
  color: black;


}
</style>
