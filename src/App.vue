<template>
  <main>
    <users-login @user-login="addUserApp"></users-login>
    <users-list
      v-for="user in userList"
      :key="user"
      :name="user.name"
      :surname="user.surname"
      :age="user.age"
    ></users-list>
  </main>
</template>

<script>
import UsersLogin from "./components/UsersLogin.vue";
import UsersList from "./components/UsersList.vue";

export default {
  components: { UsersLogin, UsersList },
  emits: {},
  data() {
    return {
      userList: [],
    };
  },
  methods: {
    addUserApp(name, surname, age) {
      this.userList.unshift({
        id: new Date().toISOString(),
        name: name,
        surname: surname,
        age: age,
      });
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  background-color: #ccc;
}
</style>
