<template>
 <div id='main' :class= 'bodyClass'>
  <div id= 'showcase-container'>
  <Header @theme = 'changeTheme($event)' id= 'header'/>
  <div id= 'showcase'>
    <h1 id= 'lead-text'>Handcrafted,home-made masterpieces</h1>
    <form id= 'form'>
    <input type='email' id= 'email' placeholder= '  Enter your email address'>
    <div>
    <button type= 'submit' id= 'submit'> GET STARTED </button>
    </div>
    </form>
    </div>
  </div>
  <section id= 'features'>
    <div id= 'features-block'>
      <div>
        <i class="fas fa-fire fa-3x icon"></i>
      </div>
      <div id= 'details'>
        <h2>Premium Materials</h2>
        <p>lorem ipsum dolor sit amet re3jrrjj fehfrhe rehjfhe sjfue dujfbeu ryyqd</p>
      </div>
    </div>
    <div id= 'features-block'>
      <div>
        <i class="fas fa-truck fa-3x icon"></i>
      </div>
      <div id= 'details'>
        <h2>Fast Shipping</h2>
        <p>lorem ipsum dolor sit amet re3jrrjj fehfrhe rehjfhe sjfue dujfbeu ryyqd</p>
      </div>
    </div>
    <div id= 'features-block'>
      <div>
        <i class="fas fa-battery-full fa-3x icon"></i>
      </div>
      <div id= 'details'>
        <h2>Quality Assurance</h2>
        <p>lorem ipsum dolor sit amet re3jrrjj fehfrhe rehjfhe sjfue dujfbeu ryyqd</p>
      </div>
    </div>
  </section>
  <Youtube id= 'youtube'/>
  <div id= 'product-exhibition'>
    <section id= 'product' class= 'line1'>
      <img :src= "require('@/assets/product1.jpg')"   id = 'productImg' alt="product1">    
      <h3> Ferrari SF90 Stradale </h3>
      <h4> $ 900k </h4>
    </section>
    <section id= 'product' class= 'line1'>
      <img :src= "require('@/assets/product2.jpg')"   id = 'productImg' alt="product2">
      <h3> Ferrari LaFerrari </h3>
      <h4> $ 200k </h4>
    </section>
    <section id= 'product' class= 'line1'>
      <img :src= "require('@/assets/product7.jpg')"   id = 'productImg' alt="product7">
      <h3> Mercedez-benz Sedan </h3>
      <h4> $ 350k </h4>
    </section>
    <section id= 'product' class= 'line2'>
      <img :src= "require('@/assets/product4.jpg')"   id = 'productImg' alt="product4">
      <h3> Mercedez-benz C 63 AMG </h3>
      <h4> $ 550k </h4>
    </section>
    <section id= 'product' class= 'line2'>
      <img :src= "require('@/assets/product8.jpg')"   id = 'productImg' alt="product8">
      <h3> Porsche 911 Turbo S </h3>
      <h4> $ 600k </h4>
    </section>
    <section id= 'product' class= 'line2'>
      <img :src= "require('@/assets/product6.jpg')"   id = 'productImg' alt="product6">
      <h3> Mercedez-benz Cabriolet </h3>
      <h4> $ 450k </h4>
    </section>
  </div>
 </div>
 <Footer />
</template>

<script>
import Header from './components/header.vue'
import Youtube from './components/youtube.vue'
import Footer from './components/footer.vue'

export default {
  name: 'App',
  components: {
    Header, Youtube, Footer
  },
  data() {
    return {
      theme: '',
      bodyClass: 'whiteS'
    }
  },
  methods: {
    changeTheme (value) {
      this.theme = value
    }
  },
  watch: {
    theme () {
      if (this.theme === 'theme1') {
        this.bodyClass =  'blackS'
      } else if (this.theme === 'theme2') {
        this.bodyClass = 'whiteS'
      }
    }
  }
}
</script>

<style>
.whiteS {
  background: white;
  color: black;
}
.blackS {
  background: black;
  color: white;
}
#header {
  position: sticky;
  top: 0;
}
#showcase-container {
  color: white;
  background:  linear-gradient(rgba(0, 0, 0, .7), rgba(0, 0, 0, .8)), url(../public/images/showcase.jpg) no-repeat center center /cover;
}
#showcase {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
#lead-text {
  margin-bottom: 50px;
  animation-name: movefromright;
  animation-duration: 2s;
}
#form {
 justify-self: center;
 align-self: center;
 margin-bottom: 20px;
 animation-name: movefrombottom;
 animation-duration: 3s;
}
#email {
  padding: 3px 10px;
  font-size: 18px;
}
#submit {
  padding: 7px 12px;
  font-size: 17px;
  margin-top: 15px;
  margin-left: 55px;
  text-align: center;
  background: orange;
  border: none;
}
#features {
  width: 50vw;
  margin: auto;
}
#features-block {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  margin-top: 40px;
}
.icon {
  margin-right: 28px;
}
#youtube {
  margin-left: 28%;
  margin-top: 70px;
  margin-bottom: 70px;
}
#product-exhibition {
  margin-left: 14%;
  display: grid;
  grid-template-columns: repeat(3, 300px)
}
#product {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  margin: 7px 15px;
  background: #419;
  padding-bottom: 10px;
}
#productImg {
  height: 150px;
  width: 300px;
}
#product h3 {
  margin-top: 5px;
}
#product h4 {
  margin-top: 8px;
  background: #914;
  padding: 7px 16px;
  border-radius: 40px;
}
.line1 {
  animation-name: movefromleft;
  animation-duration: 2s;
}
.line2 {
  animation-name: movefromright;
  animation-duration: 2s;
  animation-delay: 2s;
}

@keyframes movefromright {
  from {
  transform: translateX(-200px);
  },
  to {
  transform: translateX(0px);
  }
}

@keyframes movefrombottom {
  from {
  transform: translateY(200px);
  },
  to {
  transform: translateY(0px);
  }
}

@keyframes movefromleft {
  from {
  transform: translateX(200px);
  },
  to {
  transform: translateX(0px);
  }
}
@media screen and (max-width: 1100px) {
  #product-exhibition {
    margin-left: 6%;
  }
  #youtube {
    margin-left: 26%;
}
}
@media screen and (max-width: 780px) {
  #product-exhibition {
    grid-template-columns: repeat(2, 320px);
    margin-left: 8%;
  }
  #productImg {
    width: 320px;
  }
  #youtube {
    margin-left: 16%;
  }
  #features {
    width: 75vw;
  }
  .icon {
    margin-right: 79px;
  }
  #features-block {
    justify-content: space-between;
  }
}
@media screen and (max-width: 550px) {
  #showcase-container {
    width: 100vw;
    background:  linear-gradient(rgba(0, 0, 0, .7), rgba(0, 0, 0, .8)), url(../public/images/showcase.jpg) no-repeat center center /cover;
    text-align: center;
  }
  #email {
    padding: 7px 12px;
    background: white;
    font-size: 18px;
    border: none;
  }
  #submit {
    margin-left: 3px;
    padding: 12px 17px;
  }
  #product-exhibition {
    grid-template-columns: repeat(1, 350px);
    margin-left: 8%;
  }
  #productImg {
    width: 350px;
  }
  #youtube {
    margin-left: 11%;
}
}
@media screen and (max-width: 400px) {
  #product-exhibition {
    margin-left: 3%;
  }
}
@media screen and (max-width: 330px) {
  #product-exhibition {
    grid-template-columns: repeat(1, 300px);
    margin-left: 3%;
  }
  #productImg {
    width: 300px;
  }
}
</style>
