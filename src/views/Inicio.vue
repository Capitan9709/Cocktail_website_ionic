<template>
    <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-menu-button color="primary"></ion-menu-button>
        </ion-buttons>
        <ion-title>Home</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Home</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="container">
        <div id="containerData">
          <strong>Welcome to "The Cocktail Website"!</strong>
          <div id="containerPresentation">
            <img src="../../resources/barman.jpg" alt="barman">
            <p>Here you will find a variety of delicious cocktail recipes that are perfect 
                for any occasion. Whether you're hosting a party or simply looking to unwind 
                after a long day, we've got you covered. Our recipes range from classic cocktails 
                like the Old Fashioned and the Manhattan, to more contemporary drinks like the 
                Cosmopolitan and the Margarita. We also have a selection of non-alcoholic 
                cocktails for those who prefer to skip the booze. 
                So, grab your shaker and let's get mixing!
            </p>
          </div>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>
  
<script setup lang="ts">
import { IonButtons, IonContent, IonHeader, IonMenuButton, IonPage, IonTitle, IonToolbar } from '@ionic/vue';

</script>
  
<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
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

#containerData{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 1em;
}

#containerPresentation{
  margin-top: 3em;
  margin-left: 1em;
  margin-right: 2em;
  width: 88%;
  display: flex;
  flex-direction: row-reverse;
  align-items: center;
  text-align: start;
  border-bottom: #8c8c8c 1px solid;
  gap: 2em;
}
#containerPresentation p{
  width: 80vh;
  margin-left: 2em;
}
#containerPresentation img{
  width: 35em;
  margin-right: 3em;
  border-radius: 0.3em;
  margin-bottom: 2em;
}
</style>
