<template>
    <div :class="classname">
      <div class="bg-white p-6 rounded shadow-xl text-left">
        <h1 class="text-sm md:text-md lg:text-lg xl:text-xl text-blue-800 font-semibold">{{ ds[index].name }} in {{ ds[index].country }} subscribed</h1>
        <p class="text-sm md:text-md lg:text-lg xl:text-xl flex">6 hours ago | 
            <svg data-v-c5edbf0e="" class="svg-inline--fa fa-shield-check text-indigo-500 ml-2 mr-1 mt-1" aria-hidden="true" focusable="false" data-prefix="fas" data-icon="shield-check" role="img" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 512 512"><path class="" fill="currentColor" d="M269.4 2.9C265.2 1 260.7 0 256 0s-9.2 1-13.4 2.9L54.3 82.8c-22 9.3-38.4 31-38.3 57.2c.5 99.2 41.3 280.7 213.6 363.2c16.7 8 36.1 8 52.8 0C454.7 420.7 495.5 239.2 496 140c.1-26.2-16.3-47.9-38.3-57.2L269.4 2.9zM369 209L241 337c-9.4 9.4-24.6 9.4-33.9 0l-64-64c-9.4-9.4-9.4-24.6 0-33.9s24.6-9.4 33.9 0l47 47L335 175c9.4-9.4 24.6-9.4 33.9 0s9.4 24.6 0 33.9z"></path>
            </svg> verified</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    mounted() {
        this.startPopupTimer();
    },
    props: {
        ds: {
            type: Array,
            default: () => [
                {name: "Andy", country: "Germany"},
                {name: "Tomas", country: "France"},
                {name: "Paul", country: "US"},
            ],
            validator: (array) => {
                return array.every(item => typeof item === 'object');
            },
        },
    },
    data() {
      return {
        showPopup: true,
        index: 0,
        classname: "fixed absolute bottom-0 left-0 flex justify-center p-4 animate-move-up z-10"
      };
    },
    methods: {
      startPopupTimer() {
        setInterval(() => {
            this.index === this.ds.length - 1 ? this.index = 0 : this.index ++;
            this.showPopup = !this.showPopup;
        }, 3000); // period of appear
      }
    },
    watch: {
        showPopup(val) {
            if(val === true) {
                this.classname = "fixed absolute bottom-0 left-0 flex justify-center p-4 animate-move-up z-10" // Show the popup
            } else {
                this.classname = "fixed absolute bottom-0 left-0 flex justify-center p-4 animate-move-down z-10"  // Hide the popup
            }
        }
    }
  };
  </script>
  
<style scoped>
/* Animation */
    @keyframes move-up {
        0% {
            transform: translateX(-100%);
            opacity: 0;
        }
        100% {
            transform: translateX(0);
            opacity: 1;
        }
    }

    @keyframes move-down {
        0% {
            transform: translateX(0);
            opacity: 1;
        }
        100% {
            transform: translateX(-100%);
            opacity: 0;
        }
    }

    .animate-move-up {
        animation: move-up 1s forwards; /* period of come */
    }

    .animate-move-down {
        animation: move-down 1s forwards; /* period of go */
    }
</style>