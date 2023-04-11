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
        <strong class="capitalize">Home</strong>
        <p>Welcome to "The Cocktail Website"! 
            Here you will find a variety of delicious cocktail recipes that are perfect 
            for any occasion. Whether you're hosting a party or simply looking to unwind 
            after a long day, we've got you covered. Our recipes range from classic cocktails 
            like the Old Fashioned and the Manhattan, to more contemporary drinks like the 
            Cosmopolitan and the Margarita. We also have a selection of non-alcoholic 
            cocktails for those who prefer to skip the booze. 
            So, grab your shaker and let's get mixing!</p>
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

#container a {
  text-decoration: none;
}
</style>
