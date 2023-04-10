<template>
    <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-menu-button color="primary"></ion-menu-button>
        </ion-buttons>
        <ion-title>About</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">About</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="container">
        <strong class="capitalize">About</strong>
        <p>At our cocktail recipe website, we are passionate about creating 
            delicious and unique drinks that are easy to make at home. 
            Our team of mixologists and cocktail enthusiasts are dedicated to 
            providing our readers with the best recipes, tips, and tricks to help 
            them become the ultimate cocktail connoisseurs. We believe that everyone 
            should be able to enjoy a perfectly crafted cocktail, regardless of their 
            level of experience. That's why we strive to make our recipes accessible 
            and easy to follow, so that anyone can create a delicious drink in the 
            comfort of their own home. So, whether you're a seasoned bartender or a 
            beginner mixologist, we invite you to explore our website and discover 
            your new favorite cocktail. Cheers!</p>
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
  top: 50%;
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
