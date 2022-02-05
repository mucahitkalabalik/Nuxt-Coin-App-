<template>
  <header id="header">
    <nav>
      <ul>
        <li>
          <a href="#home">
            <nuxt-link class="header-link" to="/">Home </nuxt-link></a
          >
        </li>
        <li>
          <a href="#coins"
            ><nuxt-link class="header-link" to="/CoinsPage"
              >All Coins
            </nuxt-link></a
          >
        </li>
        <li>
          <a href="#contact"
            ><nuxt-link class="header-link" to="/contact"
              >Contact
            </nuxt-link></a
          >
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {};
</script>

<style scoped>
#header {
  display: flex;
  flex-direction: row;
  justify-content: center;
  padding: 3px 0;
  box-shadow: 5px 5px 100px black;
  position: sticky;
  top: 0;
  background-image: linear-gradient(to left, rgb(177, 80, 80), rgb(0, 0, 0));
  z-index: 3;
}
nav ul {
  display: flex;
  justify-content: flex-end;
}
nav ul li a .header-link {
  line-height: 4rem;
  color: rgb(255, 255, 255);
  padding: 20px 20px;
  transition: 0.3s color linear 0.2s, 1s background-color;
  border-radius: 5px;
  margin-right: 1rem;
  background-color: rgba(255, 255, 255, 0.028);
}
nav ul li:hover a .header-link {
  background-color: rgba(255, 255, 255, 0.274);
  color: black;
}
</style>
