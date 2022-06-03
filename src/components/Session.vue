<script>
export default {
  name: 'Session',
  props: {
    name: String,
    title: String,
    time: String,
  },
}
</script>

<template>
  <div class="grid grid-cols-4 shadow-dark-800 mt-6">
    <div class="media">
      <img class="w-60" src="../assets/avatar-2092113_640.png" alt="">
    </div>
    <div class="session-details col-span-3">
      <div class="meta">
        <h2>{{ name }}</h2>
        <h3>{{ time }}</h3>
        <h4>{{ title }}</h4>
      </div>
      <div class="details col-span-3">
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Est perferendis itaque assumenda nemo iusto vero,
          illo
          sequi odit. Molestiae voluptas officiis, dolorem temporibus non nisi necessitatibus consectetur reiciendis?
          Quibusdam, repellat!
        </p>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Est perferendis itaque assumenda nemo iusto vero,
          illo
          sequi odit. Molestiae voluptas officiis, dolorem temporibus non nisi necessitatibus consectetur reiciendis?
          Quibusdam, repellat!
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="">

</style>
