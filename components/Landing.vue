<template>
    <div :class="classname">
      <div class="bg-white p-4 rounded shadow-md text-center">
        <h1>{{ ds[index].name }} in {{ ds[index].country }} subscribed</h1>
        <p>6 hours ago | verified</p>
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
            default: () => [],
            validator: (array) => {
                return array.every(item => typeof item === 'object');
            },
        },
    },
    data() {
      return {
        showPopup: true,
        index: 0,
        classname: "fixed bottom-0 left-0 flex justify-center p-4 animate-move-up"
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
                this.classname = "fixed bottom-0 left-0 flex justify-center p-4 animate-move-up" // Show the popup
            } else {
                this.classname = "fixed bottom-0 left-0 flex justify-center p-4 animate-move-down"  // Hide the popup
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