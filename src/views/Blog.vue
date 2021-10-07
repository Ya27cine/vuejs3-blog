<template lang="">
    <h1>Blog</h1>
    <h3>List Posts :</h3>
    <div v-for="post in posts"  :key="post.id">
        <OnePost :post="post"  />
    </div>
</template>
<script>
    import { ref } from 'vue'
    import OnePost from "../components/OnePost"
export default {
    components:{ 
                OnePost
    },
    setup() {
        // Data :
        const posts = ref([
            {
                id: 1,
                title: "Learn Angular Updated",
                content: " est simplement du faux texte employé dans la composition et la mise en page avant impression"
            },
            {
                id: 2,
                title: "Learn ReactJS",
                content: " est simplement du faux texte employé dans la composition et la mise en page avant impression."
            },
            {
                id: 3,
                title: "Learn VueJS",
                content: " est simplement du faux texte employé dans la composition et la mise en page avant impression."
            },
            {
                id: 4,
                title: "Learn CakePhp",
                content: " est simplement du faux texte employé dans la composition et la mise en page avant impression."
            },
            {
                id: 5,
                title: "Learn Spring boot",
                content: " est simplement du faux texte employé dans la composition et la mise en page avant impression."
            },
            {
                id: 6,
                title: "Learn Flask",
                content: " est simplement du faux texte employé dans la composition et la mise en page avant impression. Le Lorem Ipsum est le faux texte standard d"
            }
        ]);

        return {
            posts
        }

    }// setUp
}
</script>
<style lang="">
    
</style>