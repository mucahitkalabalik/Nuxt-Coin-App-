<template>
  <section id="coins">
    <v-data-table
      :headers="headers"
      :items="coins"
      :items-per-page="20"
      class="elevation-10 mx-15 pl-10 data-table"
      loading="true"
      align="center"
      
    >
      <template v-slot:item.image="{ item }">
        <img
          :src="item.image"
          style="width: 40px; height: 40px; margin-top: 5px"
        />
      </template>
    </v-data-table>
  </section>
</template>

<script>
import axios from "axios";
export default {
  components: {},
  data() {
    return {
      coins: [],
      headers: [
        {
          text: "Name",
          align: "start",
          sortable: false,
          value: "name",
        },
        { text: "image", value: "image" },
        { text: " current_price", value: "current_price" },
        { text: " high_24h", value: "high_24h" },
        { text: "low_24h", value: "low_24h" },
        ,
        {text:"market_cap",value:"market_cap"},
        {
          text: "price_change_percentage_24h",
          value: "price_change_percentage_24h",
        }
      ],
    };
  },
  //   async fetch() {
  //     await this.getCoins();
  //   },

  async mounted() {
    const data = axios.get(
      `https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=50&page=1&sparkline=false`
    );
    const coins = await data;
    this.coins = coins.data;
    console.log(coins.data[0]);
  },
};
</script>

<style scoped>
#coins {
  background-image: linear-gradient(to right, rgb(177, 80, 80), rgb(0, 0, 0));
  padding-top: 50px;

}

.theme--light.v-data-table {
  background-color: #ffffff29;
  color: rgba(0, 0, 0, 0.87);
}
.theme--light.v-data-table > .v-data-table__wrapper > table > tbody > tr:hover:not(.v-data-table__expanded__content):not(.v-data-table__empty-wrapper) {
    background: #eeeeee30;
}

@media (max-width:555) {
  .v-application .pl-10 {
    padding-left: 0 !important; 
}
}
</style>
