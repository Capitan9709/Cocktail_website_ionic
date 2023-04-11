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
        <h2 class="capitalize">About</h2>

        <div id="containerData">
          <div id="containerPresentation">
            <h3>Presentation</h3>
            <p>At our cocktail recipe website, we are passionate about creating 
              delicious and unique drinks that are easy to make at home.<br>
              Our team of mixologists and cocktail enthusiasts are dedicated to 
              providing our readers with the best recipes, tips, and tricks to help 
              them become the ultimate cocktail connoisseurs. We believe that everyone 
              should be able to enjoy a perfectly crafted cocktail, regardless of their 
              level of experience. <br>That's why we strive to make our recipes accessible 
              and easy to follow, so that anyone can create a delicious drink in the 
              comfort of their own home. So, whether you're a seasoned bartender or a 
              beginner mixologist, we invite you to explore our website and discover 
              your new favorite cocktail. Cheers!</p>
          </div>
          <div id="containerHistory">
            <h3>History</h3>
            <p>I created this website as a personal project to challenge 
              myself. The website is a simple one, consisting of an 
              introduction, a cocktail search engine where you can view 
              detailed preparation instructions, and an about section. 
              The website is uploaded to my GitHub repository, and I'm 
              proud of the progress I've made so far. It's been a great 
              learning experience, and I look forward to continuing to 
              develop my skills in web development.</p>
          </div>
          <div id="containerObjetive">
            <h3>Objetive</h3>
            <p>The main goal of this website is to provide a simple and 
              easy-to-use platform for cocktail enthusiasts to 
              search and explore different cocktail recipes. 
              It serves as a personal project to challenge myself 
              and hone my web development skills while creating a 
              useful tool for others. The website features a clean 
              and straightforward design with a homepage, a search 
              bar for finding cocktails by name or ingredient, and a 
              detailed page for each cocktail's recipe and instructions. 
              Additionally, the website includes an "About" section to 
              provide more information about the project and its creator. 
              All of these features are available on my GitHub page, 
              where others can view and contribute to the project if 
              they wish.</p>
          </div>
          <div id="containerDevelopment">
            <h3>Development</h3>
            <p>I started by researching and choosing the technologies 
              and frameworks to use, ultimately deciding on Ionic and 
              Vue.js. From there, I designed the basic layout of the 
              page and began coding the necessary components.<br>
              One of the main challenges I faced was working with 
              the CocktailDB API to retrieve and display cocktail 
              information. I had to figure out how to make the necessary 
              API calls and properly parse and format the returned data.<br>
              I also faced some design challenges, such as ensuring that the 
              divs displaying the cocktail information were consistently sized 
              and that the spinner remained centered on the page regardless of 
              other content.<br>
              Overall, the development process was a great learning 
              experience and allowed me to test and improve my coding 
              skills while creating a functional and user-friendly web page.
            </p>
          </div>
          <div id="containerSummary">
            <h3>Summary</h3>
            <p>
              In summary, this website was created as a personal project 
              to challenge myself and showcase my skills. It is a simple 
              website with a homepage, a cocktail search feature that 
              displays detailed preparation information, and an about 
              page. The website was developed using Ionic framework with 
              Vue.js and utilizes an API to fetch cocktail data. The 
              design and layout of the website were carefully considered 
              to provide a user-friendly experience. Additionally, the 
              website is hosted on my GitHub page, which allows for easy 
              access and sharing. Overall, this project allowed me to 
              develop my coding abilities and create a functional and 
              visually appealing website.
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
  display: flex;
  flex-direction: column;
  align-items: center;
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 1em;
  line-height: 1.2em;
  color: #8c8c8c;
  margin: 0;
}
#containerData{
  width: 100%;
  display: flex;
  flex-direction: column;
}

#containerPresentation{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: start;
}
#containerPresentation h3{
  padding-left: 3em;
  padding-right: 3em;
}
#containerPresentation p{
  width: 80vh;
  padding-bottom: 2em;
  padding-left: 5em;
  padding-right: 5em;
  text-align: start;
}

#containerHistory{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: end;
}
#containerHistory h3{
  padding-left: 3em;
  padding-right: 3em;
}
#containerHistory p{
  width: 80vh;
  padding-bottom: 2em;
  padding-left: 5em;
  padding-right: 5em;
  text-align: start;
}

#containerObjetive{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: start;
}
#containerObjetive h3{
  padding-left: 3em;
  padding-right: 3em;
}
#containerObjetive p{
  width: 80vh;
  padding-bottom: 2em;
  padding-left: 5em;
  padding-right: 5em;
  text-align: start;
}

#containerDevelopment{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: end;
}
#containerDevelopment h3{
  padding-left: 3em;
  padding-right: 3em;
}
#containerDevelopment p{
  width: 80vh;
  padding-bottom: 2em;
  padding-left: 5em;
  padding-right: 5em;
  text-align: start;
}

#containerSummary{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
#containerSummary h3{
  padding-left: 3em;
  padding-right: 3em;
}
#containerSummary p{
  width: 80vh;
  padding-bottom: 2em;
  padding-left: 5em;
  padding-right: 5em;
  text-align: center;
}
</style>
