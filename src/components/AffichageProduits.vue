<!--Affichage des produits de la liste-->
<script setup>
const { produit } = defineProps(["produit"]);
</script>

<template>
    <div id="produit">
        <div id="nomProd">{{ produit.afficherNom() }}</div>
        <img :src="produit.photo" alt="Image" />
        <!-- alt = texte alternatif si l'image ne peut être affichée-->
        <br>
        <div id="qteProd">{{ produit.afficherQte() }}</div>
        <button id="moins" @click="$emit('eventDown', produit)">-</button>
        <button id="plus" @click="$emit('eventUp', produit)">+</button>
        <br>
        <button id="supp" @click="$emit('eventSupp', produit.id)">Supprimer</button>
    </div>

</template>

<style>
img {
    width: 150px;
    height: 80px;
}

#moins:hover {
    width: 20px;
    background-color: rgb(230, 46, 46);
    border-radius: 5px;
}

#plus:hover {
    width: 20px;
    background-color: rgb(111, 147, 26);
    border-radius: 5px;
}

.supp {
    height: 50px;
    cursor: pointer;
    font-family: Arial, sans-serif;
    font-weight: bold;
}

#supp:hover {
    background-color: #0570FF;
    border-radius: 5px;
    color: rgb(255, 255, 255);
}

#produit {
    margin-top: 20px;
    margin-right: 30px;
    background-color: #e7ecf0;
    padding: 0.5em;
    border-radius: 10px;
    font-family: Arial, sans-serif;
    font-size: 0.5em;
    text-align: center;
    align-items: center;
    justify-content: center;
    border: solid 1px transparent;
    /* pour l'hover */
}

#produit:hover {
    background-color: #e7ecf0;
    border-radius: 10px;
    border: solid 2px #0570FF;
}

#nomProd {
    font-weight: bold;
}

#qteProd {
    font-family: 'Courier New', Courier, monospace;
    font-weight: normal;
}
</style>