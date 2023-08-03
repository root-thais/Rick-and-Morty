<template>
  <div class="card">
    <img
      class="image img-responsive img-rounded"
      :src="props.character.image"
      alt=""
    />
    <h3 class="text-success">{{ props.character.name }}</h3>
    <p>{{props.character.desc}}</p>
  </div>
</template>

<script setup>

 const props = defineProps({
    character: {
        name: String,
        desc: String,
        age: Number,
        gender: String,
        image: String
    }
 })

</script>

<style scoped>
.card{
  color: white;
  background-color: rgba(76, 136, 238, 0.22);
  padding: 1.5rem;
  border: solid 1px rgb(233, 237, 248);
  border-radius: 15px;
  align-items: center;
  
}

.card .image{
  max-width: 100%;
}
</style>