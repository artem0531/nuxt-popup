<template>
  <Landing :ds="this.ds"/>
</template>

<script>
import Landing from './components/Landing';

export default {
  data() {
    return {
      ds: [
        {name: "Andy", country: "Germany"},
        {name: "Tomas", country: "France"},
        {name: "Paul", country: "US"},
      ]
    }
  }
}
</script>