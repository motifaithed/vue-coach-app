<template>
    <section>
        FILTER
    </section>
    <section>
        <div class="controls">
            <button>Refresh</button>
            <router-link to="/register">Register as a Coach</router-link>
        </div>
        <ul v-if="hasCoaches">
            <li v-for="coach in listOfCoaches" :key="coach.id">{{ coach.firstName }}</li>
        </ul>
        <h3 v-else>There are no coach listed!</h3>
    </section>
</template>
<script>

    export default {
        computed:{
            listOfCoaches(){
                return this.$store.getters['coaches/coaches'];
            },
            hasCoaches(){
                return this.$store.getters['coaches/hasCoaches']
            }
        }
    }
</script>
<style scoped>
    ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.controls {
  display: flex;
  justify-content: space-between;
}
</style>