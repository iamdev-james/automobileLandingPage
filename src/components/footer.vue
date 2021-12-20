<template>
  <div id= 'footer'>
    <section id= 'section-1'>&copy; 2021</section>
    <section id= 'section-2'> 
        <i class="fab fa-twitter social"></i>
        <i class="fab fa-facebook social"></i>
        <i class="fab fa-linkedin-in social"></i>
    </section>
  </div>
</template>
<script>
export default { 
}
</script>
<style scoped>
  #footer {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 15px 50px;
    background: #333;
    color: white;
  }
  #section-1 {
    margin-left: 12px;
  }
  .social {
    padding: 15px;
    border: 1px solid #fff;
    border-radius: 50%;
    margin-right: 7px;
  }
</style>