<template>
  <div class="container">
    <SearchPage /> 
  </div>
 
    <!--page home-->
    <!-- <div v-if="page == 'home'" class="container home">
      <h1>HOME</h1>
      <div class="row">
        <div class="col col-xs-12">
          <img class="img-section"
            src="https://rickandmortyapi.com/api/character/avatar/90.jpeg"
            alt=""
          />
        </div>

        <div class="col col-xs-6">
          <div class="rick-and-morty">
            <h3>10%</h3>
            <p>lorem ipsum lorem ipsum lorem ipsum</p>
          </div>
        </div>

        <div class="col col-xs-6">
          <div class="rick-and-morty">
            <h3>33%</h3>
            <p>lorem ipsum lorem ipsum lorem ipsum</p>
          </div>
        </div>

        <div class="col col-xs-12">
          <div class="filter">
            <p>Ajuste a disposição</p>
            <input class="disposition" type="range" />
            <br />
            <p>Ajuste a cor</p>
            <input class="disposition" type="range" />
          </div>
        </div>
      </div>
    </div> -->

    <!--page list character-->
    <!-- <div v-else-if="(page == 'list-character')" class="container">
      <div class="row row-cols-2">
        <div class="col col-12 p-1">
          <h1 class="card-title">All characters</h1>
          <p class="card-subtitle">4 characters on your list</p>
        </div>
      </div>
      <div class="row row-cols-2">
        <div class="col col-xs-6 p-1">
          <CharacterItem
            :character="{
              name: 'rick Sanchez',
              desc: 'Descrição',
              image: 'https://rickandmortyapi.com/api/character/avatar/1.jpeg',
            }"
          />
        </div>

        <div class="col col-xs-6 p-1">
          <CharacterItem
            :character="{
              name: 'Morty Smith',
              desc: 'Descrição',
              image: 'https://rickandmortyapi.com/api/character/avatar/2.jpeg',
            }"
          />
        </div>

        <div class="col col-xs-6 p-1">
          <CharacterItem
            :character="{
              name: 'Summer Smith',
              desc: 'Descrição',
              image: 'https://rickandmortyapi.com/api/character/avatar/3.jpeg',
            }"
          />
        </div>

        <div class="col col-xs-6 p-1">
          <CharacterItem
            :character="{
              name: 'Beth Smith',
              desc: 'Descrição',
              image: 'https://rickandmortyapi.com/api/character/avatar/4.jpeg',
            }"
          />
        </div>

       

      </div>
      <button
        class="btn btn-primary btn-lg"
        type="button"
        @click="page = 'add-character'">To character</button>
     
        
      
    </div> -->
    <!--Page search-->

    <!-- <div v-else-if="page == 'search'" class="container search">
      
      <div class="col col-xs-12">
        <h4>Search</h4>
        <input id="search" type="search" placeholder=" Search your character">
        <button id="btnsearch" class="btn btn-success" type="button"><img class="icon-search img-fluid" src="src/assets/img/pesquisa.png" alt=""></button>
      </div>
      
      <div>
        <h1>teste</h1>
        <br>
        <br>
        <br>
        <br>
        <h1>teste</h1>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>  
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        


      </div>
      
    </div> -->

    <!--page register-->

    <!-- <div v-else-if="page == 'add-character'" class="container register-character">
      <div class="col col-xs-12">
        <h1>Page register</h1>
        <br />
        <p>Character's Name</p>
        <input id="newchar" type="text" placeholder=" Enter the character's name" />
        <br />
        <br>
        <p>Author of the voice</p>
        <input id="newchar" type="text" placeholder=" Enter the author's voice" />
        <br />
        <button class="btn btn-primary btn-lg btn-search" type="button">To add</button>
      </div>
    </div> -->

    <!--nav menu-->
    <div class="container">
      <div class="menu">
        <div class="col col-xs-3" @click="page = 'home'">
          <img class="img-fluid" src="src/assets/img/casa (1).png" alt="" />
        </div>
        <div class="col col-xs-3" @click="page = 'search'">
          <img class="img-fluid" src="src/assets/img/pesquisa.png" alt="" />
        </div>
        <div class="col col-xs-3" @click="page = 'list-character'">
          <img class="img-fluid" src="src/assets/img/cardapio.png" alt="" />
        </div>
        <div class="col col-xs-3">
          <img class="img-fluid" src="src/assets/img/perfil-de-usuario.png" alt="" />
        </div>
      </div>
    </div>
</template>

<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import CharacterItem from "./components/CharacterItem.vue";
import SearchPage from "./components/SearchPage.vue";
import { ref } from "vue";

const page = ref("home");


</script>


<style scoped>

.container.home{
  color: white;
}
.home .img-section{
  margin-bottom: -4.5rem;
    padding-right: 0;
    padding-left: 0;
}

.home .cover-img {
    object-fit: cover;
    max-height: 48rem;
    border-radius: 5                                                                                                         px;
    width: 100%;
}

.rick-and-morty{
    background: rgb(2,0,36);
    background: linear-gradient(180deg, rgb(9 9 10 / 82%) 0%, rgb(10 10 27 / 61%) 54%, rgb(42 59 63 / 56%) 100%);
    border-radius: 15px;
    text-align: -webkit-center;
    padding: 1.3rem 1rem;
}

.filter{
    background: #161615;
    font-size: medium;
    border-radius: 15px;
    margin-top: 1rem;
    padding: 2.5rem 2rem;
}

.disposition{
  -webkit-appearance: none;
    background: #494847;
    outline: none;
    appearance: none;
    cursor: pointer;
    width: 50%;
    height: 20px;
    border-radius: 9px;

}

.container.search{
  color: white;
  border-radius: 15px;
  
}

#search {
  background-color: #4d80ee8e;
  border: solid 5px green;
  border-radius: 15px;
  padding: 8px;
  
  
}

#search::placeholder {
  color: white;
}

#btnsearch{
  width: 4rem;
  height: 1.5rem;
  
}

#icon-search{
  
  padding-top: 10rem;
}

.container.search img{
  width: 10%;
  
}


.container.register-character{
  color: white;
}

#newchar{
  border-radius: 15px;
  padding: 6px;
}
.image {
  max-width: 100px;
  max-height: 80px;
}

.card-title {
  margin-bottom: 8%;
  color: white;
  text-align: left;
}

.card-subtitle {
  color: white;
  text-align: left;
}
.new-card {
  color: white;
  background-color: rgba(76, 136, 238, 0.22);
  padding: 1rem;
  border-radius: 15px;
  border: dotted rgb(25, 192, 221);
  text-align: center;
}

.btn {
  width: 90%;
  margin-bottom: 15%;
  border-radius: 15px;
  margin-top: 6%;
}

.menu {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  display: flex;
  background: rgb(2, 154, 170);
  background: linear-gradient(
    90deg,
    rgba(2, 154, 170, 0.5662640056022409) 0%,
    rgba(35, 112, 203, 0.7539390756302521) 100%
  );
  margin-top: 27px;
  justify-content: center;
}
.menu .img-fluid {
  height: 55px;
  padding: 1rem;
}
</style>
