<template>
  <section id="home" class="home">
    <img class="img-btc" :src="img_btc" />
    <img class="img-eth" :src="img_eth" />

    <v-container class="check-input elevation-10">
      <div class="card-container">
        <div class="coin-input">
          <v-text-field color="black" label="Coin name" v-model="coinname" @keyup.enter="getChangeCoin">
          </v-text-field>
          <v-btn class="get-btn" @click="getChangeCoin">Get Coin Info</v-btn>
        </div>
        <div class="coin-show elevation-13" v-if="coin">
          <img class="elevation-10 rounded-pill info-image" :src="coin.image" />
          Coin name
          <h3>{{ coin.name }}</h3>
          Price
          <h3>{{ coin.current_price.toFixed(5) }} $</h3>
          <div class="detail d-flex" align="center" justify="center">
            <div class="min-high">
              High Price 24h
              <h4>{{ coin.high_24h.toFixed(5) }} $</h4>
              Min Price 24h
              <h4>{{ coin.low_24h }} $</h4>
            </div>
            <div class="rank">
              Coin Rank
              <h4>{{ coin.market_cap_rank }}</h4>
              Coin Price Change 24h
              <h4>{{ coin.price_change_24h.toFixed(7) }} $</h4>
            </div>
          </div>
        </div>
        <div class="coin-show elevation-13" v-else>
          <h1>Coin bulunamadı</h1>
        </div>
      </div>
    </v-container>
  </section>
</template>

<script>
import axios from "axios";
export default {
  data: () => ({
    img_btc:
      "https://assets.coingecko.com/coins/images/1/large/bitcoin.png?1547033579",
    img_eth:
      "https://assets.coingecko.com/coins/images/279/large/ethereum.png?1595348880",
    coin: {
      name: "ethereum",
      image:
        "https://assets.coingecko.com/coins/images/279/large/ethereum.png?1595348880",
      current_price: 3400,
      market_cap_rank: 2,
      high_24h: 3600,
      low_24h: 3000,
      price_change_24h: -1,
    },
    coinname: "",
    detail_show: true,
  }),
  async fetch() {
    await this.getCoin();
  },
  methods: {
    async getCoin() {
      const data = axios.get(
        `https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=shiba-inu&order=market_cap_desc&per_page=1&page=1&sparkline=false%27`
      );
      const coins = await data;
      console.log(coins)
      this.coin = coins.data[0];
    },
    async getChangeCoin() {
      axios
        .get(
          `https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=${this.coinname}&order=market_cap_desc&per_page=1&page=1&sparkline=false%27`
        )
        .then((response) => {
          if (response.data.length) {
            this.coin = response.data[0];
          } else {
            this.coin = null;
          }
        });
    },
  },
};
</script>

<style scoped>
#home {
  background-image: linear-gradient(to right, rgba(179, 56, 56, 0.904), rgb(0, 0, 0));
  width: 100%;
}
.home {
  padding-top: 3rem;
}
.img-btc {
  -webkit-animation-name: btc; /* Chrome, Safari, Opera */
  -webkit-animation-duration: 4s; /* Chrome, Safari, Opera */
  animation-name: btc;
  animation-duration: 6s;
  position: absolute;
  animation-iteration-count: infinite;
  margin-top: 5rem;
  margin-left: 1rem;
  height: 150px;
  width: 150px;
}
.img-eth {
  -webkit-animation-name: eth; /* Chrome, Safari, Opera */
  -webkit-animation-duration: 4s; /* Chrome, Safari, Opera */
  animation-name: eth;
  animation-duration: 6s;
  position: absolute;
  animation-iteration-count: infinite;

  height: 150px;
  width: 150px;
}
@-webkit-keyframes btc {
  0% {
    left: 0px;
    top: 10px;
  }
  50% {
    left: 0px;
    top: 200px;
  }
  100% {
    left: 0px;
    top: 10px;
  }
}
@-webkit-keyframes eth {
  0% {
    right: 0px;
    bottom: 20px;
  }
  50% {
    right: 0px;
    bottom: 200px;
  }
  100% {
    right: 0px;
    bottom: 20px;
  }
}

.check-input {
  background-color: rgba(255, 255, 255, 0.138);
  min-height: 50rem;
  padding-top: rem;
  z-index: 2;
  padding-left: 5rem;
  border-radius: 10rem;
  max-width: 70%;
}
.card-container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 3.5rem;
}
.coin-input {
  width: 25rem;
}
.coin-show {
  background-image: linear-gradient(
    to bottom,
    rgb(24, 24, 24),
    rgb(87, 87, 87)
  );
  width: 35rem;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  min-height: 40rem;
  margin-left: 2rem;
  border-radius: 10rem;
  color: rgb(141, 141, 141);
  transition: color 0.5s linear;
  max-width: 27rem;
}
.coin-show:hover {
  background-image: linear-gradient(
    to bottom,
    rgb(0, 0, 0),
    rgb(136, 136, 136)
  );
  color: black;
}
.rank {
  padding-left: 4rem;
}
h1 {
  color: white;
}
h2 {
  color: white;
}
h3 {
  color: white;
}
@media (max-width: 1024px) {
  .img-btc {
    display: none;
  }
  .img-eth {
    display: none;
  }
  .check-input {
    max-width: 90%;
  }
}
@media (max-width: 555px) {
  .card-container {
    display: block;
    justify-content: center;
    align-items: center;
    padding-top: 3.5rem;
  }
  .check-input {
    padding-left: 0;
    padding-right: 3.5rem;
  }
  .coin-input {
    margin-left: 4rem;
    margin-bottom: 2rem;
    max-width: 15rem;
  }
  .get-btn{
    margin-left: 2rem;
  }
  .coin-show{
    max-width: 100%;
  }
  .info-image{
    max-width: 11rem;
  }
 
}
</style>
