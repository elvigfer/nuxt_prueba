<template>
    <nav>
        <ul>
            <li>
                <NuxtLink to="/"> <MaterialIconHome/> </NuxtLink>
            </li>
            <li>
                <NuxtLink to="/about"> About </NuxtLink>
            </li>
        </ul>
        <div class="user"
        @click="panelIsOpen = !panelIsOpen"></div>
        <nav class="panel"
        v-show="panelIsOpen"></nav>
    </nav>
</template>
<script>
export default{
    data(){
        return{
            panelIsOpen: false
        }
    },
    
}</script>
<style lang="postcss">
    nav{
        @apply bg-gray-200;
        display: flex;
        justify-content: space-between;}
        ul{
            display: flex;
            flex-direction: row;
            
        }
        li{
                @apply p-5;
            }
        .user{
            @apply rounded-full m-3 w-12 h-12 bg-gray-400;
        }
        .panel{
            @apply  w-40 h-60 bg-white;
            position: absolute;
            top: 200px;
            right: 5px;
        }
    .nuxt-link-exact-active{
        font-weight: bold;
    }

</style>