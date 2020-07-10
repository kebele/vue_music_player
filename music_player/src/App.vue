<template>
  <div id="app">
    <header>
      <h1>music player</h1>
    </header>
    <main>
      <section class="player">
        <h2 class="song-title">{{ current.title }} - <span>{{ current.artist }}</span>
        </h2>
        <div class="control">
          <button class="prev">prev</button>
          <button class="play" v-if="!isPlaying" @click="play">play</button>
          <button class="pause" v-else @click="pause">pause</button>
          <button class="next">next</button>
        </div>
      </section>
    </main>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      current : {},
      index : 0,
      isPlaying : false,
      songs : [
        {
          title : 'acoustic breeze',
          artist : 'sergio ramos',
          src : require('./assets/acousticbreeze.mp3')
        },
        {
          title : 'a new beginning',
          artist : 'karim benzema',
          src : require('./assets/anewbeginning.mp3')
        },
        {
          title : 'jazz frenchy',
          artist : 'raphael varane',
          src : require('./assets/jazzyfrenchy.mp3')
        },
      ],
      player : new Audio()
    }
  },
  methods: {
    play(song){
      if(typeof song.src !== "undefined"){
        this.current = song;
        this.player.src = this.current.src
      }
      this.player.play();
      this.isPlaying = true;
    },
    pause(){
      this.player.pause();
      this.isPlaying = false;
    }
  },
  created(){
    this.current = this.songs[this.index];
    this.player.src = this.current.src;
    //buradaki ilişkiye dikkat, this.current dediğinde bu func. içindeki atamaya dikkat, datadaki current değil
    // this.player.play();
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
