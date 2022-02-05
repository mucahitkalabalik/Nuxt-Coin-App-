<template>
  <section id="contact" class="contact">
    <div class="icons-container">
      <a href="https://www.instagram.com/mucahit.kalabalik/" target="_blank"><div class="instagram"></div> </a>
      <a href="https://twitter.com/mucahit19_" target="_blank"><div class="twitter"></div> </a>
      <a href="https://github.com/mucahitkalabalik" target="_blank"><div class="github"></div> </a>
      <a href="https://www.facebook.com/mucahitkalabalik/" target="_blank"><div class="facebook"></div> </a>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
.contact {
  background-image: linear-gradient(to right, rgb(177, 80, 80), rgb(0, 0, 0));
  width: 100%;
}
.icons-container{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    gap: 5rem;
    flex-wrap: wrap;
}
.facebook {
  background-image: url("../assets/svg file/icons8-facebook.svg");
  background-size: cover;
  height: 100px;
  width: 100px;
  cursor: pointer;
}
.twitter {
  background-image: url("../assets/svg file/icons8-twitter.svg");
  background-size: cover;
  height: 100px;
  width: 100px;
  cursor: pointer;
}
.instagram {
  background-image: url("../assets/svg file/icons8-instagram.svg");
  background-size: cover;
  height: 100px;
  width: 100px;
  cursor: pointer;
}
.github {
  background-image: url("../assets/svg file/icons8-github.svg");
  background-size: cover;
  height: 100px;
  width: 100px;
  cursor: pointer;
}

.facebook:hover    {
    background-color: rgb(9, 70, 148);
    border-radius: 50%;
}   
.instagram:hover    {
     background-color: rgb(167, 86, 86);
    border-radius: 40%;
}   

.github:hover    {
    background-color: rgba(5, 5, 5, 0.583);
    border-radius: 50%;
}   

.twitter:hover    {
     background-color: rgba(72, 154, 160, 0.782);
    border-radius: 45%;
}   


</style>
