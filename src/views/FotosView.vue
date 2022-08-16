<template>
    <h1>Galeria de fotos</h1>
    <router-link :to="{name: 'fotos', params: { id:item } }"
    v-for="(item,i) of fotos" :key="i">
        <button>Foto {{item}}</button>
    </router-link>
    
    <Foto/>
    <button @click="home">Home</button>
    <button @click="anterior">Anterior</button>
    <button @click="siguiente">Siguiente</button>
</template>

<script>
    import Foto from '@/components/Foto.vue';

    export default{
        components:{
            Foto,
        },
        data(){
            return{
                fotos:[1,2,3,20,31]
            }
        },
        methods:{
            home(){
                this.$router.push('/');
            },
            anterior(){
                this.$router.go(-1);
            },
            siguiente(){
                this.$router.go(1);
            }
        }
    }
</script>