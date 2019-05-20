<template>
  <div id="app">
    <router-view/> <!-- View -->

    <div id="footer">
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/music">Music</router-link></li>
        <li><a href="https://medium.com/@nookskill">Medium</a></li>
        <li><a href="https://github.com/nookskill">Github</a></li>
        <li><a href="https://linkedin.com/in/supayut-raksuk">Linkedin</a></li>
        <li><a href="mailto:nookskill@hotmail.com">Mail</a></li>
      </ul>
    </div>
  </div>
</template>

<style>
  body {
    background: #1f2833;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #c5c6c7;
  }
  #nav {
    padding: 50px;
    font-size: 25px;
  }

  #nav a {
    font-weight: bold;
    color: #c5c6c7;
  }

  #nav a.router-link-exact-active {
    color: #66fcf1;
  }

  #nav ul {
    padding: 0;
  }

  #nav li {
    display: inline-block;
    list-style-type: none;
    padding-left: 30px;
  }

  #head {
    padding: 50px;
    font-size: 96px;
    font-weight: bold;
  }

  #footer {
    background: #1f2833;
    overflow: hidden;
    position: fixed;
    bottom: 0;
    width: 100%;
  }

  #footer a {
    color: #c5c6c7;
  }

  #footer ul {
    padding: 0;
  }

  #footer li {
    display: inline-block;
    list-style-type: none;
    padding-left: 15px;
  }


  @media only screen and (max-width: 540px) {
    #nav li {
      padding-left: 0;
      padding-right: 0;
      display: block;
      font-size: 30px;
      margin: 20px;
    }

    #nav ul {
      border-left: thin solid;
      border-left-color: #45a29e;
    }

    #head {
      padding: 0;
      padding-bottom: 0;
      font-size: 45px;
      font-weight: bold;
    }

    #footer ul {
      padding: 0;
      list-style-type: none;
    }

    #footer li {
      width: 25%;
      /*float: left;*/
    }
  }

</style>

