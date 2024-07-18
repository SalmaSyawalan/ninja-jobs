<template>
<div v-if="job">
    <h1>{{ job.title }}</h1>
    <p>the job id is {{ id }}</p>
</div>
<h1>Job Details Page</h1>

</template>

<script>
export default {
    props: ['id'],
    data(){
        return{
            job: null
        }
    },
    mounted(){
        fetch('http://localhost:3000/jobs/' + this.id)
            .then(res => res.json())
            .then(data => this.job = data)
            .catch(err => console.log(err.message))
        console.log(this.job)
    }
}
</script>

<style>

</style>
