<template>
  <div class="home page">
    <tuto-v-model></tuto-v-model>
    <h1 class="title my-hello">Hello Vue ; )</h1>
    <img alt="Vue logo" src="../assets/logo.png">
    <my-hello :msg="['hello tout le monde']"></my-hello>
    <p>
      <b>Challenge1:</b><br>
      Créer un composant ToggleSquare.<br>
      Ce composant est un simple carré de couleur. Au click, il devient noir.
      <br> Après un second click, il reprend sa couleur initiale...<br>
      et ainsi de suite !
    </p>
    <hr>
    <ToggleSquare></ToggleSquare>
    <hr>
    <p>
        <b>Challenge 2:</b><br> 
        Créer un composant UsersList prenant un tableau d'users en prop.<br>
        Importer UsersList dans un composant Users.<br>
        Déplacer le v-for du composant User dans le template d'UsersList.<br>
        Une méthode getUserNameLength est exécutée @click sur chaque user<br>
        Elle affiche la longueur du nom de l'user cliqué, dans la console.<br>
    </p>
    <hr>
    <p>
        <b>Challenge 3:</b><br>
        Créer un composant UserForm permettant de créer des users (1 à la fois).<br>
        Importer UserForm dans un composant Users.<br>
        Il contient deux champs de formulaire input pour les propriétés name et astro, et un bouton pour valider.<br>
        @click: effectuer un test pour que les deux propriétés soient renseignées. 
        Puis utiliser les évènement custom pour émettre le nouvel user généré vers le composant parent.<br>
        Utiliser une méthode pour ajouter le nouvel user à la liste d'users.
    </p>
    <hr>
<div class="challenge">
  <b>Challenge 4</b>:<br>
  Créer un composant CustomMessage(msg, css)<br>
  CustomMessage écoute ($on) le bus d'events ($ebus).<br>
  CustomMessage affiche le message émis ($emit... msg) dans un élément portant une classe (css) parmi:
  Importer CustomMessage dans App.<br>
  <ul>
    <li>success</li>
    <li>warning</li>
    <li>error</li>
  </ul>
  Utiliser customMessage pour afficher les messages relatifs à la création d'user (composant UserForm).<br>
</div>
<hr>
    <Cousin></Cousin>
  </div>
</template>

<script>
import Cousin from "@/components/Cousin.vue";
// @ is an alias to /src
import TutoVModel from "@/components/ComprendreVModel.vue";
import myHello from "@/components/myHello.vue";
import ToggleSquare from "@/components/ToggleSquare.vue";
export default {
  created() {
    this.$ebus.$on("hello-je-pars-en-bus", payload => {
        console.log("@home", payload);
    });
  },
  name: "home",
  components: {
    myHello,
    ToggleSquare,
    TutoVModel,
    Cousin
  }
};
</script>