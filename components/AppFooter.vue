<template>
  <footer class="footer" id="footer">
    <div class="container">
      <ul>
        <li>
          <a href="https://www.instagram.com/mucahit.kalabalik/" target="_blank"
            ><div class="instagram svg-footer"></div>
          </a>
        </li>
        <li>
          <a href="https://twitter.com/mucahit19_" target="_blank"
            ><div class="twitter svg-footer"></div>
          </a>
        </li>
        <li>
          <a href="https://github.com/mucahitkalabalik" target="_blank"
            ><div class="github svg-footer"></div>
          </a>
        </li>
        <li>
          <a href="https://www.facebook.com/mucahitkalabalik/" target="_blank"
            ><div class="facebook svg-footer"></div>
          </a>
        </li>
      </ul>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style scoped>
footer {
 background-image: linear-gradient(to right, rgba(179, 56, 56, 0.904), rgb(0, 0, 0));
  min-height: calc(100vh * 0.12);
}
.container ul {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
}
.container ul li {
    margin-right: 4rem;
}

.facebook {
  background-image: url("../assets/svg file/icons8-facebook.svg");
  background-size: cover;
  height: 75px;
  width: 75px;
  cursor: pointer;
}
.twitter {
  background-image: url("../assets/svg file/icons8-twitter.svg");
  background-size: cover;
  height: 75px;
  width: 75px;
  cursor: pointer;
}
.instagram {
  background-image: url("../assets/svg file/icons8-instagram.svg");
  background-size: cover;
  height: 75px;
  width: 75px;
  cursor: pointer;
}
.github {
  background-image: url("../assets/svg file/icons8-github.svg");
  background-size: cover;
  height: 75px;
  width: 75px;
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
     background-color: rgba(62, 175, 184, 0.782);
    border-radius: 45%;
}   

@media (max-width:555px) {
    .svg-footer{
        height: 30px;
        width: 30px;
    }
}

</style>
