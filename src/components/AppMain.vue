<script >
import AppSearch from './AppSearch.vue';
import CharactersList from './CharactersList.vue';


export default{
  components: {
    AppSearch,
    CharactersList

  },
  data(){
    return{
        character : [],
    }
  },
  methods:{
    getCharacters(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then(function (response){
            console.log(response);
        })
        .catch(function (error){
            cnsole.log(error);
        })
        .finally(function (){

        });
    }
  },
  created (){
    this.getCharacters();
  }
}
</script>

<template>
    <main>
        <h1>
            MAIN
        </h1>
        <AppSearch/>
        <CharactersList/>
    </main>
</template>

<style lang="scss" scoped>



</style>