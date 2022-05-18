<template>
<article>
    <div>
        <img src="/imagen.jpg" alt="card">
    </div>
    <button @click="playpause"><MaterialIconPlay v-show="!isPlaying"/> <MaterialIconPause v-show="isPlaying"/>{{ title }}</button>
</article>
</template>
<script>
import {Howl, Howler} from 'howler';
export default{
    props:['title'],
    data(){
        return{
            sound: '',
            isPlaying: false
        }
    },
    mounted(){
        this.sound = new Howl({
      src: ['/audios/trouble.mp3']
    });
    },
    methods: {
        playpause(){
            if(this.sound.playing()){
                this.sound.pause();
                this.isPlaying = false;
            } else{this.sound.play();
                this.isPlaying= true;}
        }
    }
}
</script>
<style lang="postcss">
    article{
        @apply w-1/4 m-10;}
        img{
            @apply h-32;
            object-fit: cover;
        }
        button{
            background-color: beige;
            @apply w-full p-3 my-5;
        }
    
</style>