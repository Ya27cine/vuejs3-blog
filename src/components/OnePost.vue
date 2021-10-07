<template >
<hr>
    <h2> {{ post.title }}</h2>
    <p> {{ extrait }} </p>
</template>

<script>
import {computed} from 'vue'
export default {
    props: ['post'],
    setup(props) {
        
        const extrait = computed( () => props.post.content.substring(0, 15)+ '...');

        return {
            extrait
        }
    }
}
</script>
<style lang="">
    
</style>