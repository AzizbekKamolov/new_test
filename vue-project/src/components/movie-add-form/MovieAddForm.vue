<template>
  <div class="movie-add-from">
    <h3>Yangi kino qo'shish</h3>
    <form class="d-flex add.form" action="#" v-on:submit.prevent>
      <input
        type="text"
        class="form-control new-movie-label"
        placeholder="Qanday kino?"
        :value="name"
        @input="name = $event.target.value"
      />
      <input
        type="text"
        class="form-control new-movie-label"
        placeholder="Necha marotaba ko'rilgan?"
        :value="viewers"
        @input="viewers = $event.target.value"
      />
      <button class="btn btn-outline-dark" @click="addMovie">Qo'shish</button>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "",
      viewers: "",
    };
  },
  methods: {
    addMovie(e) {
      const newMovie = {
        id: Date.now(),
        name: this.name,
        viewers: this.viewers,
        favourite: false,
        like: false,
      };
      if(this.name.length == 0 || this.viewers.length == 0){
        alert("Ma'lumotlarni to'liq kiriting")
        return true;
      }
      this.$emit("createMovie", newMovie);
      this.name = ''
      this.viewers = ''
    },
  },
};
</script>
<style>
.movie-add-from {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>