<template>
  <div class="app">
    <div class="content">
      <ApplicationInfo/>
      <div class="search-panel">
        <SearchPanel/>
        <AppFilter/>
      </div>
    </div>
  </div>
</template>
<script>
import AppFilterVue from '../app-filtr/AppFilter.vue';
import ApplicationInfo from '../app-info/ApplicationInfo.vue';
import SearchPanel from '../serach-panel/SearchPanel.vue';
import AppFilter from '../app-filtr/AppFilter.vue';
import MovieList from '../movie-list/MovieList.vue';
export default{
  components:{
    ApplicationInfo,
    SearchPanel,
    AppFilter,
    MovieList
  }
}
</script>

<style>
  .app{
    height: 100vh;
    color: #000;
  }
  .content{
    width: 1000px;
    min-height: 700px;
    background-color: #fff;
    margin: 0 auto;
    padding: 5rem 0;
  }
  .search-panel{
    margin-top: 2rem;
    padding: 1.5rem;
    background-color: #fcf5f5;
    border-radius: 4px;
    box-shadow: 15px 15px 15px rgba(0, 0, 0, .15);
  }
</style>
