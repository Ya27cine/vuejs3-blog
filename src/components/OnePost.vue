<template >
<hr>
    <h2 @click="show = !show"> {{ post.title }}</h2>
    <p v-if="show"> {{ extrait }} </p>
</template>

<script>
import {ref, computed, onMounted, onUpdated, onUnmounted} from 'vue'
export default {
    props: ['post'],
    setup(props) {
        
        // Life cycle hooks :
        onMounted( () => console.log('One Post mounted') );

        onUpdated( () => console.log('One Post update') );

         onUnmounted( () => console.log('One Post unmounted') );


       // onMounted( () => console.log() );

        const show  = ref(true);

        const extrait = computed( () => props.post.content.substring(0, 17)+ '...');

        return {
            extrait,
            show
        }
    }
}
</script>
<style lang="">
    
</style>