<template>
    <div class="hello">
        <button @click="test">aaa</button>
    </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  created(){
    // eslint-disable-next-line
    console.log(process.env.VUE_APP_BASE_URL || process.env.BASE_URL)
  },
  methods: {
    test() {
      axios
        .get(
          `${process.env.VUE_APP_BASE_URL || process.env.BASE_URL}api/values`
        )
        .then(response => {
          // eslint-disable-next-line
          console.log(response);
        });
    }
  }
};
</script>

