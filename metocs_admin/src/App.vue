
<template>
  <div class="hello">
    <person/>
  </div>
</template>


<script lang="ts">
import Person from "@/components/Person.vue";
export default {
  name: 'app',
  components: {Person}
}

</script>

<style scoped>

.hello{
  background-color: aquamarine;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;

}


</style>
