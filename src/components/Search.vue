<template>
    <div id="search-container">
        
        <input type="text" v-model="query" v-on:input="$emit('query-change', query)">
        
    </div>
</template>

<script>
import { uuid } from 'vue-uuid';

export default ({
    name: 'Search',
    data(){
        return{
            query: ''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();

            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            };

            this.title = '',
            this.$emit('add-todo', newTodo)
        }
    }

})
</script>

<style scoped>
    #search-container{
        width: 600px;
        margin: 0 auto;
    }
    input{
        padding: 10px;
        width: 100%;
        outline: none;
    }
</style>