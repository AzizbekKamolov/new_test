<template>
  <div class="app">
    <div class="content">
      <ApplicationInfo
        :allMoviesCount="movies.length"
        :favouuriteMoviesCount="movies.filter((c) => c.favourite).length"
      />
      <div class="search-panel">
        <SearchPanel />
        <AppFilter />
      </div>
      <MovieList :movies="movies" @onToggle="onToggleHandler"/>
      <MovieAddForm @createMovie="createMovie" />
    </div>
  </div>
</template>
<script>
import ApplicationInfo from "../app-info/ApplicationInfo.vue";
import SearchPanel from "../serach-panel/SearchPanel.vue";
import AppFilter from "../app-filtr/AppFilter.vue";
import MovieList from "../movie-list/MovieList.vue";
import MovieAddForm from "../movie-add-form/MovieAddForm.vue";
export default {
  components: {
    ApplicationInfo,
    SearchPanel,
    AppFilter,
    MovieList,
    MovieAddForm,
  },
  data() {
    return {
      movies: [
        {
          id: 1,
          name: "Omar",
          viewers: 811,
          favourite: false,
          like: false,
        },
        {
          id: 2,
          name: "Harry poter",
          viewers: 1000,
          favourite: true,
          like: true,
        },
        {
          id: 3,
          name: "Halk",
          viewers: 988,
          favourite: true,
          like: false,
        },
        {
          id: 4,
          name: "Omar",
          viewers: 811,
          favourite: false,
          like: false,
        },
      ],
    };
  },
  methods: {
    createMovie(item) {
      this.movies.push(item);
    },
    onToggleHandler({id, prop}) {
      this.movies.map((item) => {
        if (item.id == id) {
          return {...item, [prop]: !item[prop]}
          // if(prop == 'like'){
          //   item.like = !item.like;
          // }else{
          //   item.favourite = !item.favourite;
          // }
        }
        return item;
      });
    },
  },
};
</script>

<style>
.app {
  height: 100vh;
  color: #000;
}
.content {
  width: 1000px;
  min-height: 700px;
  background-color: #fff;
  margin: 0 auto;
  padding: 5rem 0;
}
.search-panel {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
