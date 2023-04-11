<template>
    <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-menu-button color="primary"></ion-menu-button>
        </ion-buttons>
        <ion-title>Cocktails</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Cocktails</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="container">
        <!-- <strong class="capitalize">Cocktails</strong> -->

        <!-- Search by Name -->
        <ion-item class="inputs">
          <ion-input aria-label="filterName" placeholder="Search by Name" v-model="filterName" @keyup.enter="searchByName"></ion-input>
          <ion-button @click="searchByName">Search</ion-button>
        </ion-item>

        <!-- Search by ingredient -->
        <ion-item class="inputs">
          <ion-input aria-label="filterIngredient" placeholder="Search by Ingredient" v-model="filterIngredient" @keyup.enter="searchByIngredient"></ion-input>
          <ion-button @click="searchByIngredient">Search</ion-button>
        </ion-item>

        <div id="cocktailsContainer">

          <ion-spinner id="spinnerPrincipal" v-if="loaded === false" name="crescent"></ion-spinner>

          <div class="cocktail" v-for="(cocktail, i) in cocktails" :key="i">
            <h2>{{ cocktail.strDrink }}</h2>
            <img :src="cocktail.strDrinkThumb" alt="cocktail image">
            <h3 v-if="cocktail.strAlcoholic != undefined">Is Alcoholic: {{ cocktail.strAlcoholic === 'Alcoholic' ? 'Yes' : 'No' }}</h3>
            <h4 v-if="cocktail.strCategory != undefined">Category: {{ cocktail.strCategory }}</h4>
            <h4 v-if="cocktail.strGlass != undefined">Recommended Glass: {{ cocktail.strGlass }}</h4>
            <p class="instructions" v-if="cocktail.strInstructions != undefined">Instructions: {{ cocktail.strInstructions }}</p>
            
            <ion-button expand="block" @click="showMore(cocktail.idDrink)">Open</ion-button>
        
            <ion-modal :is-open="isOpen" v-for="(cocktailDetail, index) in cocktailModal" :key="index">
              <ion-header>
                <ion-toolbar>
                  <ion-title>{{ cocktailDetail.strDrink }}</ion-title>
                  <ion-buttons slot="end">
                    <ion-button @click="setOpen(false)">Close</ion-button>
                  </ion-buttons>
                </ion-toolbar>
              </ion-header>
              <ion-content class="ion-padding">
                <ion-spinner v-if="loadedModal === true" name="crescent"></ion-spinner>
                <div class="modalContent">
                  <div class="modalContentImg">
                    <img class="imageDetail" :src="cocktailDetail.strDrinkThumb" alt="cocktail image">
                  </div>
                  <div class="modalContentText">
                    <h3>Is {{ cocktailDetail.strAlcoholic === 'Alcoholic' ? 'an' : 'not an'}} Alcoholic Drink</h3>
                    <h4>Category: {{ cocktailDetail.strCategory }}</h4>
                    <h4>Recommended Glass: {{ cocktailDetail.strGlass }}</h4>
                    <h4>Ingredients:</h4>
                    <ul>
                      <li v-if="cocktailDetail.strIngredient1 != null">{{ cocktailDetail.strIngredient1 }} - {{ cocktailDetail.strMeasure1 }}</li>
                      <li v-if="cocktailDetail.strIngredient2 != null">{{ cocktailDetail.strIngredient2 }} - {{ cocktailDetail.strMeasure2 }}</li>
                      <li v-if="cocktailDetail.strIngredient3 != null">{{ cocktailDetail.strIngredient3 }} - {{ cocktailDetail.strMeasure3 }}</li>
                      <li v-if="cocktailDetail.strIngredient4 != null">{{ cocktailDetail.strIngredient4 }} - {{ cocktailDetail.strMeasure4 }}</li>
                      <li v-if="cocktailDetail.strIngredient5 != null">{{ cocktailDetail.strIngredient5 }} - {{ cocktailDetail.strMeasure5 }}</li>
                      <li v-if="cocktailDetail.strIngredient6 != null">{{ cocktailDetail.strIngredient6 }} - {{ cocktailDetail.strMeasure6 }}</li>
                      <li v-if="cocktailDetail.strIngredient7 != null">{{ cocktailDetail.strIngredient7 }} - {{ cocktailDetail.strMeasure7 }}</li>
                      <li v-if="cocktailDetail.strIngredient8 != null">{{ cocktailDetail.strIngredient8 }} - {{ cocktailDetail.strMeasure8 }}</li>
                      <li v-if="cocktailDetail.strIngredient9 != null">{{ cocktailDetail.strIngredient9 }} - {{ cocktailDetail.strMeasure9 }}</li>
                      <li v-if="cocktailDetail.strIngredient10 != null">{{ cocktailDetail.strIngredient10 }} - {{ cocktailDetail.strMeasure10 }}</li>
                      <li v-if="cocktailDetail.strIngredient11 != null">{{ cocktailDetail.strIngredient11 }} - {{ cocktailDetail.strMeasure11 }}</li>
                      <li v-if="cocktailDetail.strIngredient12 != null">{{ cocktailDetail.strIngredient12 }} - {{ cocktailDetail.strMeasure12 }}</li>
                      <li v-if="cocktailDetail.strIngredient13 != null">{{ cocktailDetail.strIngredient13 }} - {{ cocktailDetail.strMeasure13 }}</li>
                      <li v-if="cocktailDetail.strIngredient14 != null">{{ cocktailDetail.strIngredient14 }} - {{ cocktailDetail.strMeasure14 }}</li>
                      <li v-if="cocktailDetail.strIngredient15 != null">{{ cocktailDetail.strIngredient15 }} - {{ cocktailDetail.strMeasure15 }}</li>
                    </ul>
                    <h4>Instructions:</h4>
                    <p>{{ cocktailDetail.strInstructions }}</p>
                  </div>
                </div>
                
              </ion-content>
            </ion-modal>
          
          </div>
        

        </div>
      </div>
    </ion-content>
  </ion-page>
</template>
  
<script setup lang="ts">
import { IonCard, IonCardHeader, IonCardTitle, IonCardContent, IonModal, IonSpinner, IonButton, IonLabel, IonItem, IonInput, IonButtons, IonContent, IonHeader, IonMenuButton, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import { OverlayEventDetail } from '@ionic/core/components';
import { ref } from 'vue';

const filterName = ref('');
const filterIngredient = ref('');
const inputText = ref('');
var loaded = ref(true);
var cocktails = ref([]);
var isOpen = ref(false);
var loadedModal = ref(true);
var cocktailModal = ref('');

function setOpen(value: boolean) {
  isOpen.value = value;
}

async function searchByName(){
  filterIngredient.value = '';
  inputText.value = filterName.value;
  loaded.value = false;
  try{
    if(inputText.value != ''){
      if(loaded.value === false){
        const response = await fetch(`https://www.thecocktaildb.com/api/json/v1/1/search.php?s=${inputText.value}`);
        var data = await response.json();
        console.log(data.drinks);
        cocktails.value = data.drinks;
        console.log(cocktails.value);
        loaded.value = true;
      }else{
        console.log('loaded');
      }
    }
  }
  catch(error){
    console.log(error);
  }
}

async function searchByIngredient(){
  filterName.value = '';
  inputText.value = filterIngredient.value;
  loaded.value = false;
  try{
    if(inputText.value != ''){
      if(loaded.value === false){
        const response = await fetch(`https://www.thecocktaildb.com/api/json/v1/1/filter.php?i=${inputText.value}`);
        var data = await response.json();
        console.log(data);
        cocktails.value = data.drinks;
        loaded.value = true;
      }else{
        console.log('loaded');
      }
    }
  }
  catch(error){
    console.log(error);
  }
}

async function showMore(cocktail){
  setOpen(true);
  loadedModal.value = false;
  try{
    if(cocktail != ''){
      if(loadedModal.value === false){
        const response = await fetch(`https://www.thecocktaildb.com/api/json/v1/1/lookup.php?i=${cocktail}`);
        var data = await response.json();
        console.log(data);
        cocktailModal.value = data.drinks;
        loaded.value = true;
        console.log(cocktailModal.value);
      }else{
        console.log('loaded');
      }
    }
  }
  catch(error){
    console.log(error);
  }
}

</script>
  
<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  margin-top: 31em;
  height: 100%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

#container a {
  text-decoration: none;
}
.inputs{
  margin-top: 1em;
  margin-bottom: 1em;
}
#cocktailsContainer {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: start;
  justify-content: center;
  margin-top: 2em;
  margin-bottom: 5em;
}
#spinnerPrincipal{
  margin-top: 10em;
}
.cocktail {
  width: 300px;
  margin: 1em;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 1em;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}
.modalContent{
  display: flex;
  flex-direction: columns;
  flex-wrap: wrap;
  align-items: start;
  justify-content: center;
}
.imageDetail{
  width: 30vh;
}
.instructions {
  height: 20vh;
  overflow: auto;
}
.instructions::-webkit-scrollbar {
  width: 10px;
}

.instructions::-webkit-scrollbar-track {
  background: #f1f1f1;
}

.instructions::-webkit-scrollbar-thumb {
  background: #888;
  border-radius: 5px;
}

.instructions::-webkit-scrollbar-thumb:hover {
  background: #555;
}
</style>
