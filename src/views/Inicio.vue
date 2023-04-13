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
      <ion-refresher slot="fixed" @ionRefresh="handleRefresh($event)">
        <ion-refresher-content></ion-refresher-content>
      </ion-refresher>
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
          <div id="containerInstructions">
            <div id="containerInstructionsData">
              <h3>Instructions:</h3>
              <p>
                To keep seeing more drinks, go to the cocktail section.
                <ul>
                  <li>
                    On desktop, it's located on the left.
                  </li>
                  <li>
                    On mobile, you need to tap on the three bars and you will find it there.
                  </li>
                </ul> 
              </p>
            </div>
            <div id="containerInstructionsImage">
              <img src="../../resources/manual.png" alt="instructions">
            </div>
          </div>
          <div id="containerPopularDrinks">
            <h3>Popular Drinks</h3>
            <div id="containerPopularDrinksList">

              <div id="containerPopularDrinksList1" class="popularDrink">
                <img src="../../resources/mojito.jpg" alt="Mojito">
                <p>Mojito</p>
              </div>
              <div id="containerPopularDrinksList2" class="popularDrink">
                <img src="../../resources/oldfashioned.jpg" alt="Old Fashioned">
                <p>Old Fashioned</p>
              </div>
              <div id="containerPopularDrinksList3" class="popularDrink">
                <img src="../../resources/longisland.jpg" alt="Long Island Tea">
                <p>Long Island Tea</p>
              </div>
              <div id="containerPopularDrinksList4" class="popularDrink">
                <img src="../../resources/negroni.jpg" alt="Negroni">
                <p>Negroni</p>
              </div>
              <div id="containerPopularDrinksList5" class="popularDrink">
                <img src="../../resources/whiskeysour.jpg" alt="Whiskey Sour">
                <p>Whiskey Sour</p>
              </div>
              <div id="containerPopularDrinksList6" class="popularDrink">
                <img src="../../resources/drymartini.jpg" alt="Dry Martini">
                <p>Dry Martini</p>
              </div>
              <div id="containerPopularDrinksList7" class="popularDrink">
                <img src="../../resources/daiquiri.jpg" alt="Daiquiri">
                <p>Daiquiri</p>
              </div>
              <div id="containerPopularDrinksList8" class="popularDrink">
                <img src="../../resources/margarita.jpg" alt="Margarita">
                <p>Margarita</p>
              </div>

            </div>
          </div>
          <div id="containerPopularIngredients">
            <h3>Popular Drinks</h3>
            <div id="containerPopularIngredientsList">

              <div id="containerPopularIngredientsList1" class="popularIngredient">
                <img src="../../resources/Vodka.png" alt="Vodka">
                <p>Vodka</p>
              </div>
              <div id="containerPopularIngredientsList2" class="popularIngredient">
                <img src="../../resources/Gin.png" alt="Gin">
                <p>Gin</p>
              </div>
              <div id="containerPopularIngredientsList3" class="popularIngredient">
                <img src="../../resources/Rum.png" alt="Rum">
                <p>Rum</p>
              </div>
              <div id="containerPopularIngredientsList4" class="popularIngredient">
                <img src="../../resources/Tequila.png" alt="Tequila">
                <p>Tequila</p>
              </div>

            </div>
          </div>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>
  
<script setup lang="ts">
import { IonRefresher, IonRefresherContent, IonButtons, IonContent, IonHeader, IonMenuButton, IonPage, IonTitle, IonToolbar } from '@ionic/vue';

const handleRefresh = (event: CustomEvent) => {
  setTimeout(() => {
    window.location.reload();
    event.detail.complete();
  }, 2000);
};

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
  width: 90%;
  display: flex;
  flex-direction: row-reverse;
  justify-content: center;
  align-items: center;
  text-align: start;
  border-bottom: #8c8c8c 1px solid;
  gap: 2em;
}
@media screen and (max-width: 750px) {
  #containerData{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 1em;
  }
  #containerPresentation{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 0;
  }
  #containerPresentation img{
    width: 50%;
  }
  #containerPresentation p{
    font-size: 20px;
    line-height: 1.3;
    padding-bottom: 2em;
    max-width: 100%;
  }
}
#containerPresentation p{
  width: 80vh;

}
#containerPresentation img{
  width: 50vh;
  border-radius: 0.3em;
  margin-bottom: 2em;
}

#containerInstructions{
    width: 90%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 1em;
    padding-bottom: 2em;
    border-bottom: #8c8c8c 1px solid;
}
#containerInstructions li{
  text-align: start;
  list-style: none;
}
#containerInstructionsImage{
  width: 50%;
}
#containerInstructionsImage img{
  margin-top: 2em;
  width: 20vh;
  border-radius: 5px;
  padding: 1em;
  background-color: #242323;
  box-shadow: 4px 4px 7px #000000;
}
#containerInstructionsData{
  width: 50%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
@media screen and (max-width: 750px) {
  #containerInstructions{
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  #containerInstructions li{
    text-align: center;
  }
  #containerInstructionsImage, #containerInstructionsData{
    width: 100%;
  }
}
#containerPopularDrinks {
  margin-top: 0.5em;
  display: flex;
  flex-direction: column;
  width: 90%;
  border-bottom: #8c8c8c 1px solid;
  margin-bottom: 2em;
}

#containerPopularDrinksList {
  margin-top: 2.8em;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 1.8em;
}
@media screen and (max-width: 750px) {
  #containerPopularDrinksList {
    grid-template-columns: repeat(2, 1fr);
  }
}

.popularDrink {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 1em;
  border-radius: 5px;
  padding: 1em;
  background-color: #242323;
  box-shadow: 4px 4px 7px #000000;
}

.popularDrink img {
  max-width: 100%;
  height: auto;
  margin-bottom: 1em;
  border-radius: 5px;
}

.popularDrink p {
  font-weight: bold;
  text-align: center;
}

#containerPopularIngredients {
  display: flex;
  flex-direction: column;
  border-bottom: #8c8c8c 1px solid;
  margin-bottom: 2em;
  width: 90%;
}

#containerPopularIngredientsList {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  text-align: center;
}
@media screen and (max-width: 750px) {
  #containerPopularIngredientsList {
    grid-template-columns: repeat(2, 1fr);
  }
}
.popularIngredient{
  margin-bottom: 1em;
}
.popularIngredient img {
  width: 25vh;
  height: auto;
}

.popularIngredient p {
  margin: 10px 0;
  font-weight: bold;
}

</style>
