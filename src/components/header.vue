<template>
  <div id= 'header'>
    <section id= 'header-nav'>
      <img :src='require("@/assets/speedy.png")' id= 'header-img' >
      <i id='headerName'>Luxury Cars </i>
    <div @click = 'toggleTheme()' id= 'changeTheme'>
      <div v-if= 'theme1' class= 'theme theme1'></div>
      <div v-if= 'theme2' class= 'theme theme2'></div>
    </div>
    <div @click= 'toggleNav()' id= 'nav-icon'><i class="fas fa-bars"></i></div>
    </section>
    <section v-show= 'showNav' id='nav-bar'>
      <a href= '#' class= 'nav-link nav-linksec1'>Features</a>
      <a href= '#' class= 'nav-link nav-linksec2'>Pricing</a>
      <a href= '#' class= 'nav-link nav-linksec1'>Contact</a>
    </section>
  </div>
</template>
<script>
export default {
  name: 'app',
  data() {
    return {
      showNav: true,
      theme1: false,
      theme2: true
    }
  },
  methods: {
    toggleTheme () {
      if (this.theme1) {
        this.theme2 = true
        this.theme1 = false
        this.$emit('theme', 'theme1')
      } else {
        this.theme2 = false
        this.theme1 = true
        this.$emit('theme', 'theme2')
      }
    },
    toggleNav () {
      if (this.showNav) {
        this.showNav = false
      } else {
        this.showNav = true
      }
    }
  },
  mounted() {
    if (window.screen.availWidth <= 900) {
      this.showNav = false
    } else {
      this.showNav = true
    }
  }
}
</script>
<style scoped>
  #header {
    width: 100vw;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 15px;
    position: fixed;
    background: inherit;
    box-shadow: 1.5px 1.5px 2px black;
  }
  #header-img {
    height: 65px;
    width: 75px;
    color: white;
  }
  #header-nav {
    display: inline-flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  #headerName {
    font-size: 30px;
    font-weight: 700;
  }
  #nav-bar {
    margin-right: 20px;
    display: inline-flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-end;
    transition: all ease-in-out 3s;
  }

  @keyframes movefromleft {
  from {
   transform: translateX(200px);
   },
  to {
   transform: translateX(0px);
   }
  }

  @keyframes movefromright {
  from {
   transform: translateX(-200px);
   },
  to {
   transform: translateX(0px);
   }
}
  .nav-link {
    margin-left: 40px;
    padding: 8px 18px;
    transition: all ease 1s;
  }
  .nav-linksec1 {
    animation-name: movefromleft;
    animation-duration: 2s;
  }
  .nav-linksec2 {
    animation-name: movefromright;
    animation-duration: 2s;
  }
  .nav-link:hover {
    background: #363;
    border-radius: 15px;
    transform: scale(1.002)
  }
  a {
    text-decoration: none;
    font-size: 18px;
    display: inline;
    color: white;
  }
  #nav-icon {
    display: none;
  }
  #changeTheme {
    width: 50px;
    padding: 2.5px 3px;
    display: flex;
    justify-content: space-between;
    margin-left: 450px;
    padding-bottom: 3px;
    border-radius: 40px;
    background: white;
  }
  .theme {
    display: inline-block;
    margin-bottom: 0px;
    padding: 8px 10px;
    margin-right: 2px;
    background: black;
    border-radius: 65px;
  }
  .theme1 {
    background: black;
  }
  .theme2 {
    background: skyblue;
    margin-left: 20px;
  }
  @media screen and (max-width: 700px) {
    #header {
      flex-direction: column;
    }
    #header-img {
    height: 55px;
    width: 80px;
    color: white;
    padding-right: 0px;
    }
    #nav-bar {
      display: inline-flex;
      padding: 10px 15px;
      flex-direction: column;
    }
    #nav-icon {
      display: inline;
      margin-right: 25px;
    }
    .nav-link {
      padding: 8px 13px;
      font-size: 19px;
    }
  #changeTheme {
      margin-left: 0px;
    }
    #header-nav {
      width: 100vw;
    }
  }
</style>
