<template>
  <div class="user-container">
    <label for="name">Imię</label>
    <input type="text" placeholder="Wpisz imię" v-model="userName" />
    <label for="surname">Nazwisko</label>
    <input type="text" placeholder="Wpisz nazwisko" v-model="userSurname" />
    <label for="age">Wiek</label>
    <input type="text" placeholder="Wpisz wiek" v-model="userAge" />
    <button @click="addUser" class="accept">Dodaj użytkownika</button>
  </div>
</template>

<script>
export default {
  emits: ["user-login"],
  data() {
    return {
      userName: "",
      userSurname: "",
      userAge: null,
    };
  },

  methods: {
    addUser() {
      this.$emit("user-login", this.userName, this.userSurname, this.userAge);
    },
  },
};
</script>

<style scoped>
div.user-container {
  width: 300px;
  height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  background-color: #aaa;
}
</style>
