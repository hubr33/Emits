<template>
  <div class="user-list">
    <div class="one-user">
      <p>{{ name }}</p>
      <p>{{ surname }}</p>
      <p>{{ age }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    surname: {
      type: String,
      required: true,
    },
    age: {
      type: String,
      required: true,
    },
  },
  data() {
    return {};
  },
};
</script>

<style scoped>
div.user-list {
  width: 300px;
  height: 400px;
  background-color: azure;
}

.one-user {
  display: flex;
  justify-content: space-evenly;
  background-color: #888;
  padding: 8px 0;
}
</style>
