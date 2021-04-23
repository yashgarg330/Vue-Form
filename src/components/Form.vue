<template>
  <div class="container">
    <form>
      <div class="row">
        <label for="name">Name</label>
        <input type="text" name="name" id="name" v-model="form.name" />
        <span> <button class="btn">Copy</button> </span>
      </div>
      <div class="row">
        <label for="age">Age</label>
        <input type="number" name="age" id="age" v-model="form.age" />
      </div>
      <div class="row">
        <label for="email">Email</label>
        <input type="email" name="email" id="email" v-model="form.email" />
      </div>
      <div class="row">
        <input v-on:click="postData" type="submit" value="Submit" />
      </div>
    </form>
  </div>

</template>

<script>

export default {
  name: "Form",
  data() {
    return {
      form: {
        name: "",
        age: null,
        email: "",
      },
    };
  },
  methods: {
    postData(e) {
      e.preventDefault()
      console.log("My data", this.form);
    },
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 4px;
}
.row {
  padding: 5px 0px;
}
label {
  margin-right: 10px;
}
input {
  background-color: skyblue;
  padding: 2px 7px;
}
input[type="text"] {
  margin-right: 5px;
}
input[type="number"] {
  margin-left: 11px;
  width: 100px;
}
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
input[type="email"] {
  margin-bottom: 5px;
  width: 200px;
}
input[type="submit"] {
  margin-left: 51px;
  cursor: pointer;
}
.btn {
  background-color: white;
  border: 0;
  cursor: pointer;
}
</style>
