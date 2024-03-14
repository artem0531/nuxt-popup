<template>

  <Fomo/>
  
</template>

<script>
import Fomo from './components/Fomo.vue';

export default {
  data() {
    return {
      ds: [
        {name: "Andy", country: "Germany"},
        {name: "Tomas", country: "France"},
        {name: "Paul", country: "US"},
        {name: "aAndy", country: "Germany"},
        {name: "Taomas", country: "France"},
        {name: "Paaul", country: "US"},
      ]
    }
  }
}
</script>