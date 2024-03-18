<template>
  <Section class="app">
    <div class="px-4 mx-auto sm:px-6 lg:px-8 max-w-7xl pb-2">
      <div class="max-w-2xl mx-auto text-center">
        <h2 class="mt-4 text-sm md:text-xl font-normal text-gray-600 mb-2">
          <!-- <span class="gradient-text font-bold">AI-powered</span> tattoo designer -->
          Create the perfect tattoo design with your personal tattoo artist
        </h2>
        <h1
          class="text-4xl font-bold tracking-tight text-gray-700 sm:text-5xl xl:text-5xl sm:tracking-tight"
        >
          <!-- Create the perfect tattoo design. -->
          <span class="gradient-text font-bold">AI-powered</span> tattoo
          generator
        </h1>
        <section class="bg-white">
          <div class="px-4 mx-auto sm:px-6 lg:px-8 max-w-7xl">
            <div class="grid grid-cols-4 gap-3 mt-8">
              <div>
                <img
                  class="w-full rounded-sm"
                  src="@/assets/img/cat-ai-tattoo.jpg"
                  alt="cat ai tattoo"
                />
              </div>

              <div>
                <img
                  class="w-full rounded-sm"
                  src="@/assets/img/wolf-ai-tattoo.jpg"
                  alt="wolf ai tattoo"
                />
              </div>

              <div>
                <img
                  class="w-full rounded-sm"
                  src="@/assets/img/lion-ai-tattoo.jpg"
                  alt="lion ai tattoo"
                />
              </div>

              <div>
                <img
                  class="w-full rounded-sm"
                  src="@/assets/img/roses-ai-tattoo.jpg"
                  alt="roses ai tattoo"
                />
              </div>
            </div>
          </div>
        </section>
        <p class="mt-6 text-lg leading-7 text-black/70 lg:leading-8">
          If you have an idea for a tattoo but can't find the right design, let
          our AI generate tattoo ideas for you within seconds. Create the
          perfect design based on what you like, and get unlimited design
          options.
        </p>
        <!-- <div class="mt-8">

          <AuthGoogleButton class="mx-auto" />
        </div> -->

        <div
          class="mt-10 mx-auto max-w-md text-center flex items-center justify-center gap-x-6"
        >
          <a href="https://www.tattoosai.com/auth/signup">
            <ButtonGradient size="base" class="mx-auto px-8">
              Design your tattoo
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="ml-2 w-4 h-4"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="m8.25 4.5 7.5 7.5-7.5 7.5"
                />
              </svg>
            </ButtonGradient>
          </a>
          <button size="base" class="p-3 flex mx-auto px-8 border border-gray-300 rounded-lg" @click="this.onToggle">
            <svg data-v-4ed79550="" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-4 h-4 text-black/50 mt-1 mr-1.5"><path fill-rule="evenodd" d="M2 10a8 8 0 1116 0 8 8 0 01-16 0zm6.39-2.908a.75.75 0 01.766.027l3.5 2.25a.75.75 0 010 1.262l-3.5 2.25A.75.75 0 018 12.25v-4.5a.75.75 0 01.39-.658z" clip-rule="evenodd"></path></svg>
            Watch Demo              
          </button>
        </div>

        <transition name="fade" class="fixed top-0 left-0 w-full h-full flex items-center justify-center z-10">
          <div v-if="isModalVisible">
            <div
              @click="onToggle"
              class="absolute bg-black opacity-70 inset-0"
            ></div>
            <div
              class="w-full max-w-lg p-3 relative mx-auto my-auto rounded-xl shadow-lg bg-white"
            >
              <div class="text-center p-3 flex-auto justify-center leading-6">
                <Section class="tattoo-bg">
                  <div class="relative pt-16 ">
                    <video class="max-w-full w-full md:max-w-4xl mx-auto border relative z-10 border-brand-600 rounded-md shadow-lg" muted loop controls autoplay>
                    <source src="https://cdn.headline99.com/demo-tattooidea.mp4" type="video/mp4">
                      Sorry, your browser doesn't support embedded videos
                    </video>
                  </div>
                </Section>
              </div>
              <div class="p-3 mt-2 text-center space-x-4 md:block">
                <button
                  class="mb-2 md:mb-0 bg-white px-5 py-2 text-sm shadow-sm font-medium tracking-wider border text-gray-600 rounded-md hover:shadow-lg hover:bg-gray-100"
                >
                  Create your own profile pictures
                </button>
              </div>
            </div>
          </div>
        </transition>       

        <div
          class="flex mx-auto max-w-md items-center justify-center gap-3 mt-4"
          style="background-color: rgb(255, 255, 255)"
        >
          <div class="flex overflow-hidden">
            <img
              src="@/assets/img/6.png"
              alt=""
              class="inline-block h-10 w-10 rounded-full border-[3px] border-white max-w-full align-middle"
            />
            <img
              src="@/assets/img/4.png"
              alt=""
              class="inline-block h-10 w-10 rounded-full border-[3px] border-white ml-[calc(-.75rem*(1_-_0))] mr-[calc(-.75rem*0)] max-w-full align-middle"
            />
            <img
              src="@/assets/img/3.png"
              alt=""
              class="inline-block h-10 w-10 rounded-full border-[3px] border-white ml-[calc(-.75rem*(1_-_0))] mr-[calc(-.75rem*0)] max-w-full align-middle"
            />
            <img
              src="@/assets/img/5.png"
              alt=""
              class="inline-block h-10 w-10 rounded-full border-[3px] border-white ml-[calc(-.75rem*(1_-_0))] mr-[calc(-.75rem*0)] max-w-full align-middle"
            />
            <img
              src="@/assets/img/2.png"
              alt=""
              class="inline-block h-10 w-10 rounded-full border-[3px] border-white ml-[calc(-.75rem*(1_-_0))] mr-[calc(-.75rem*0)] max-w-full align-middle"
            />
          </div>
          <div class="flex">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 20 20"
              fill="currentColor"
              class="h-5 w-5 text-yellow-400 block align-middle"
            >
              <path
                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
              />
            </svg>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 20 20"
              fill="currentColor"
              class="h-5 w-5 text-yellow-400 block align-middle"
            >
              <path
                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
              />
            </svg>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 20 20"
              fill="currentColor"
              class="h-5 w-5 text-yellow-400 block align-middle"
            >
              <path
                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
              />
            </svg>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 20 20"
              fill="currentColor"
              class="h-5 w-5 text-yellow-400 block align-middle"
            >
              <path
                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
              />
            </svg>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 20 20"
              fill="currentColor"
              class="h-5 w-5 text-yellow-400 block align-middle"
            >
              <path
                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
              />
            </svg>
          </div>
        </div>

        <div
          class="mt-2 mx-auto max-w-md text-center flex items-center justify-center gap-x-6"
        >
          <p class="italic text-gray-500 text-xs">
            Join 3,672 happy customers.
          </p>
        </div>
      </div>
    </div>
  </Section>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    onToggle() {
      this.isOpen = !this.isOpen;
    }
  },
  computed: {
    isModalVisible() {
      return this.isOpen;
    }
  }
};
</script>

<style  scoped>
.gradient-text {
  background: -webkit-linear-gradient(
    60deg,
    #f79533,
    #f37055,
    #ef4e7b,
    #a166ab,
    #5073b8,
    #1098ad,
    #07b39b,
    #6fba82
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 500ms ease-out;
}
</style>
