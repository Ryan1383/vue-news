

<template>
    <div>
        <div v-for="job in jobs" :key="job.id">{{ job.title }} </div>
    </div>
</template>

<script>
    /* eslint-disable */
import { fetchJobsList } from '../api/index.js'


export default {
    data(){
        return {
            jobs: [],
        }
    },
    created(){
        fetchJobsList()
            .then( response => this.jobs = response.data )        
            .catch( error=> console.log(error));
    }
}
</script>

<style>

</style>