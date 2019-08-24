<template>
  <div class="home">
    <div class="form">
      <form>
        <label>
          Please enter dates separates by commas (ex : 4/3, 12/2, 3/5, ...):
          <input
            v-model="tag"
            type="text"
            @keyup.enter="search($event)"
          />
        </label>
      </form>
    </div>
    <div class="wrapper">
      <p v-if="loading">Loading...</p>
      <ul v-else class="image-card">
        <!-- <DateCard class="date" v-for="(date, index) in dates" :key="index"/> -->
        <li v-for="date in dates" :key="date.index">{{date}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios";
// const CancelToken = axios.CancelToken;
// const source = CancelToken.source();
// import DateCard from "@/components/DateCard.vue";

export default {
  name: "home",
  components: {
    // DateCard
  },
  data() {
    return {
      loading: false,
      tag: "",
      dates: []
    };
  },
  methods: {
    search(event) {
      console.log("Searching for: ", this.tag);
      this.dates = [];
      let values = event.target.value;
      console.log(values);
      // let valuesArray = values.split(", ");
      this.loading = true;
      // valuesArray.forEach(element => {
      //   axios
      //     .get(`http://numbersapi.com/${element}/date`, {
      //       cancelToken: source.token
      //     })
      //     .catch(function(thrown) {
      //       if (axios.isCancel(thrown)) {
      //         console.log("Request canceled", thrown.message);
      //       }
      //     })
      //     .then(response =>
      //       this.dates.push({
      //         date: element,
      //         text: response.data
      //       })
      //     )
      //     .catch(error => {
      //       console.log("An error ocurred: ", error);
      //     });
      // });
    },
    
    // fetchDate(element) {
    //   axios
    //     .get(`http://numbersapi.com/${element}/date`, {
    //       cancelToken: source.token
    //     })
    //     .catch(function(thrown) {
    //       if (axios.isCancel(thrown)) {
    //         console.log("Request canceled", thrown.message);
    //       }
    //     })
    //     .then(response =>
    //       this.dates.push({
    //         date: element,
    //         text: response.data
    //       })
    //     )
    //     .catch(error => {
    //       console.log("An error ocurred: ", error);
    //     });
    // }
  }
};
</script>

<style lang="scss" scoped>
.form {
  padding-top: 50px;
  input {
    width: 100%;
    border: none;
    background: none;
    border-bottom: 2px solid;
    margin-top: 20px;
    text-align: center;
    color: black;
  }
}

.text-centered {
  text-align: center;
}
.wrapper {
  margin: 0 auto;
  max-width: 800px;
  @media only screen and (max-width: 799px) {
    max-width: 100%;
    margin: 0 1.5rem;
  }
}
.image-card {
  list-style: none;
  margin: 0.5rem 0;
  padding: 0;
  display: flex;
  align-items: flex-start;
  flex-wrap: wrap;
}

.dates {
  margin-top: 20px;
}

.btn-go {
  padding: 0.5rem 1rem;
  font-size: 1rem;
  border-radius: 20px;
  background: transparent;
  border: none;
}
</style>
