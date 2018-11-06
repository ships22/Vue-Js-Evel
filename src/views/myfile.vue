<template>
    <div class="user page">
        <h1 class="title"> {{ title }}</h1>
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Magnam quia aperiam cumque? Molestias quae aspernatur aut rem, asperiores nostrum assumenda!
        </p>
        <h2 class="title"> Promo: Aulnay</h2>
        <p>effective promo {{ effectif }}</p>
        
        <div class="widget">
            <!-- <input type="range" min="0" max="30" @input="getEffectif($event)"
            :value="effectif"> -->
            <input type="range" min="0" max="30" v-model="limit">
        </div>
        <ul :class="{full: users.length > 24}" class="list_user">
            <li v-for="(u, n) in users" :key='n'>{{ u.Name }} is {{ u.astro }}</li>
        </ul>
        <ToggleSquare></ToggleSquare>
        <UserList v-bind:users="users"></UserList>
    </div>
</template>
<script>
import ToggleSquare from '@/components/ToggleSquare.vue';
import UserList from '@/components/UserList.vue';

export default {
               components: {
                ToggleSquare,
                UserList
            },
    data(){
        return {
            title: "Page Users !",
            limit: 0,
            effectif: 8, 
            users: [
                { Name: "Jim", astro: "leo" }, 
                { Name: "Tom", astro: "virgo" }, 
                { Name: "Me", astro: "scorpio" }, 
                { Name: "Mike", astro: "virgo" },
                { Name: "Brad", astro: "virgo" }
            ]
        }
    },
    methods: {
        // getEffectif(e){
        //     this.effectif = e.target.value;
        // }
    }
}
</script>
<style scopped>
    .full {
        color: red;
    }
</style>


