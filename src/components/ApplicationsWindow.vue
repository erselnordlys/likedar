<template xmlns:v-on="http://www.w3.org/1999/xhtml" xmlns:v-bind="http://www.w3.org/1999/xhtml">
  <div id="applications">
    <div id="header">
      <div class="applics">{{msg.applics}}</div>
      <div class="all-clients active">{{msg.allClients}}</div>
      <div class="settings"></div>
    </div>

    <div id="list">
      <div id="search">
        <div class="search-icon"></div>
        <input placeholder="ПОИСК">
        <div class="stars-num">{{msg.starsNum}}</div>
        <div class="stars-icon"></div>

      </div>
      <client v-for='item in 15'></client>
    </div>
    <div class="blanc"></div>
    <div id="button">{{msg.button}}</div>
  </div>
</template>

<script>
  import Client from './ApplicationMessage.vue'
  export default {
    name: 'ApplicationsWindow',
    data () {
      return {
        msg: {
          applics: 'ЗАЯВКИ',
          allClients: 'ВСЕ КЛИЕНТЫ',
          starsNum: '53',
          button: 'В начало'
        }
      }
    },
    components: {
      client: Client
    }
  }
</script>

<style scoped>
  #applications {
    background: #fff;
    display: flex;
    flex-direction: column;
    height: 100%;
    position: relative;
    min-width: 250px;
  }
  ::-webkit-scrollbar
  {
    width: 4px;
  }

  ::-webkit-scrollbar-track
  {
    background: rgba(0, 0, 0, 0.1);
  }

  ::-webkit-scrollbar-thumb {
    background: #65a3e5;
  }

  .blanc {
    border-top: 1px solid #d3d3d3;
    min-height: 50px;
    width: 100%;
  }

  #header {
    background: #8dbbec;
    color: white;
    cursor: pointer;
    display: flex;
    flex-direction: row;
    font-size: 16px;
    min-height: 80px;
  }

  #header div {
    align-items: center;
    display: flex;
    justify-content: center;
  }

  #header div:hover {
    background-color: #65a3e5;
  }

  .applics {
    width: 36%;
  }

  .all-clients {
    width: 53%;
  }

  .settings {
    background: url('../assets/fa-gear.png') center / 20px 20px no-repeat;
    width: auto;
    flex-grow: 1;
  }

  .active {
    background: #65a3e5;
    position: relative;
  }

  .active:after {
    border-left: 12px solid transparent;
    border-right: 12px solid transparent;
    border-top: 15px solid #65a3e5;
    bottom: -14px;
    content: '';
    left: 50%;
    margin-left: -10px;
    position: absolute;
    width: 0;
    height: 0;
  }

  #search {
    align-items: center;
    border-bottom: 1px solid #d3d3d3;
    display: flex;
    font-size: 14px;
    height: 80px;
    justify-content: center;
    padding: 0 15px;
    width: auto;
  }

  .search-icon {
    background:  url('../assets/ fa-search.png') center / 20px 20px no-repeat;
    height: 20px;
    width: 24px;
  }

  input {
    border: none;
    outline: none;
    font-size: 14px;
    flex-grow: 1;
    margin-left: 15px;
    min-width: 100px;
  }

  .stars-num {
    color: #606060;
    font-size: 14px;
    margin-left: 10px;
  }

  .stars-icon {
    background: url('../assets/fa-star.png') top / 15px 15px no-repeat;
    cursor: pointer;
    height: 18px;
    margin-left: 10px;
    width: 18px;
  }

  #list {
    height: auto;
    overflow: auto;
  }

  #button {
    align-items: center;
    background: #8dbbec;
    bottom: -20px;
    border-radius: 25px;
    color: white;
    cursor: pointer;
    display: flex;
    font-size: 18px;
    justify-content: center;
    height: 40px;
    left: 50%;
    margin-left: -90px;
    position: absolute;
    width: 180px;
  }

  #button:hover {
    background-color: #65a3e5;
  }
</style>
