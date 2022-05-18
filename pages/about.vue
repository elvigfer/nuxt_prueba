<template>
  <main>
    <banner-img :source="'/imagen2.jpg'" :alt="'imagen del mar'"/>
    <menu-principal/>
    <h1>About</h1>
    <p>Esto es una clase</p>
    <section class="tarjetas">
        <card-base v-for="item in cards"
        :key0="i"
        :title="item.title"
        />
        
    </section>
    <ul>
        <li v-for="mountain of mountains">{{ mountain.title }}</li>
      </ul>
    <div id="map-wrap" style="height: 100vh">
 <client-only>
   <l-map :zoom=13 :center="[55.9464418,8.1277591]">
     <l-tile-layer url="http://{s}.tile.osm.org/{z}/{x}/{y}.png"></l-tile-layer>
     <l-marker :lat-lng="[55.9464418,8.1277591]"></l-marker>
   </l-map>
 </client-only>
</div>
  </main>
</template>

<script>
export default {
  name: 'About',
  data() { 
      return{cards: [
      {title: 'Botón 1'},
      {title: 'Botón 2'},
      {title: 'Botón 3'},
      {title: 'Botón 4'}],
      mountains: []}
  },
  async fetch() {
      this.mountains = await fetch(
        'https://api.nuxtjs.dev/mountains'
      ).then(res => res.json())
    }
}
</script>

<style lang="postcss">
    .tarjetas{
        display: flex;
        flex-direction: row;
    }
</style>