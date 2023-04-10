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
        <strong class="capitalize">Cocktails</strong>
        <ion-item>
          <ion-input aria-label="filter" placeholder="Write Something..." v-model="filter" @keyup.enter="callApi"></ion-input>
        </ion-item>
        <ion-button @click="callApi">Buscar</ion-button>

        <div id="cocktailsContainer">
          <ion-content v-if="data.drinks">
            <ion-card v-for="cocktail in data.drinks" :key="cocktail.idDrink">
              <ion-card-header>
                <ion-card-title>{{ cocktail.strDrink }}</ion-card-title>
              </ion-card-header>
              <ion-card-content>
                <p>{{ cocktail.strAlcoholic }}</p>
              </ion-card-content>
            </ion-card>
          </ion-content>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>
  
<script setup lang="ts">
import { IonCard, IonCardHeader, IonCardTitle, IonCardContent, IonButton, IonLabel, IonItem, IonInput, IonButtons, IonContent, IonHeader, IonMenuButton, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import { ref } from 'vue';

const filter = ref('');
const inputText = ref('');
var data = "";

function printFilter(){
  inputText.value = filter.value;
}

async function callApi(){
  try{
    inputText.value = filter.value;
    const response = await fetch(`https://www.thecocktaildb.com/api/json/v1/1/search.php?s=${inputText.value}`);
    data = await response.json();
    console.log(data.drinks);
  }catch(error){
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
  top: 25%;
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
</style>
