<script>
export default {
    name: 'ProjectCard',
    props: {
        projectInfo: Object
    }
}
</script>

<template>
    <div class="card text-bg-primary mb-3 mx-5" style="width: 25%">
        <div class="card-body">
            <h5 class="card-title">{{ projectInfo.titolo }}</h5>                        
            <p class="card-text">{{ projectInfo.descrizione }}</p>
        </div>
    </div>
</template>

<style lang="scss">
@use '../style/generic';


</style>