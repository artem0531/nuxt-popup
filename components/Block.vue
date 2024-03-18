<template>
  <div class=" p-1 rounded-xl py-4">
    <div class="w-full  rounded-lg">
      <div class="flex flex-col justify-center items-center text-center">
        <Logo class="w-[100px]" />
        <!-- <h2 class="text-sm uppercase font-bold my-4 text-gray-600">
          This is a Pro component
        </h2> -->
        <h1 class="text-3xl font-bold text-black mt-4">
          Design unlimited tattoos for 7 days.
        </h1>
        <h2 class="mt-2 text-lg text-gray-700">
          <strong class="text-brand-500">391,568</strong> tattoos already generated for <strong class="text-yellow-500">5,235</strong> happy customers!
        </h2>
        <p class="text-base font-medium text-gray-700 mt-2">
          Single time payment, no subscription. Design as many tattoos as you want.
        </p>
      </div>
      <AlertWarning v-if="hasPurchasedBefore && !hasAccess" class="mt-4 max-w-lg mx-auto" title="Your access pass has expired" description="Purchase a new pass to get unlimited access again" />
      <!-- <PricingMain/> -->
      <!-- <UpgradeFeatureGrid class="my-8 max-w-lg mx-auto" /> -->
      <LoadingWrapper :is-loading="isLoading" title="Redirecting to checkout">
        <!-- <nuxt-link :to="'/checkout?priceId='+price.id" @click="toCheckout"> -->
        <ButtonGradient class="mt-4 mx-auto" @click="toCheckout('week')">
          Get 7-day access for ${{ price.week.amount }} <span class="text-xs font-normal italic ml-1.5 hidden md:flex">(one-time payment)</span>
        </ButtonGradient>

        <button class="text-gray-600 text-center mt-2 underline underline-offset-2 mx-auto text-sm w-full" @click="toCheckout('month')">
          Or, purchase 30 days access for ${{ price.month.amount }}
        </button>
        <!-- </nuxt-link> -->
      </LoadingWrapper>
      <div class="w-full text-center text-sm text-gray-700 mt-3">
        <strong class="text-green-500">One-time payment.</strong> We do not charge you ever again.
      </div>

      <!-- <p class="text-xs text-gray-500 text-center mt-8 max-w-4xl mx-auto">
        Flowponent Premium is a paid option, because most Premium Features require additional expenses from us, such as image storage and server costs. Contributions from Flowponent Premium allows us to keep the costs low and provide you with the best possible experience.
      </p> -->
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isLoading: false
    }
  },
  computed: {
    price () {
      return {
        week: {
          amount: 9.99,
          id: (this.$config.NODE_ENV === 'development') ? 'price_1LfGkgEyGZ8Ommr7RBX5oLjj' : 'price_1OZkPsDk3DbkTS0WKLU2bhQU'
        },
        month: {
          amount: 24.99,
          id: (this.$config.NODE_ENV === 'development') ? 'price_1LfZJXEyGZ8Ommr7V0i7G7Sr' : 'price_1OZkPsDk3DbkTS0WFdgWCc4B'
        }
      }
    }
  },
  methods: {
    toCheckout (plan) {
      this.$store.commit('SHOW_UPGRADE_MODAL', false)
      this.$router.push('/checkout?priceId=' + this.price[plan].id)
    }
  }

}
</script>

<style scoped>

.gradient-bg {
    content: "";
    background: linear-gradient(60deg,#f79533,#f37055,#ef4e7b,#a166ab,#5073b8,#1098ad,#07b39b,#6fba82);
    -webkit-animation: animatedgradient 3s ease infinite alternate;
    animation: animatedgradient 3s ease infinite alternate;
    background-size: 300% 300%;
}

@keyframes animatedgradient {
0% {
    background-position: 0% 50%;
}
50% {
    background-position: 100% 50%;
}
100% {
    background-position: 0% 50%;
}
}
</style>
