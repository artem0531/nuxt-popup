<template>
    <div v-if="!hasAccess" :class="classname">
      <div class="bg-white p-6 rounded shadow-2xl text-left">
        <h1 class="text-sm md:text-sm lg:text-sm xl:text-sm text-blue-800 font-light">{{ ds[index].name }} in <i :class="countryClass"></i><span class="font-semibold">{{ ds[index].country }}</span> purchased</h1>
        <p class="text-gray-500 text-xs md:text-xs lg:text-xs xl:text-xs flex">{{ ds[index].time }} ago | 
            <svg data-v-c5edbf0e="" class="svg-inline--fa fa-shield-check text-indigo-500 ml-2 mr-1 mt-1" aria-hidden="true" focusable="false" data-prefix="fas" data-icon="shield-check" role="img" xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 512 512"><path class="" fill="currentColor" d="M269.4 2.9C265.2 1 260.7 0 256 0s-9.2 1-13.4 2.9L54.3 82.8c-22 9.3-38.4 31-38.3 57.2c.5 99.2 41.3 280.7 213.6 363.2c16.7 8 36.1 8 52.8 0C454.7 420.7 495.5 239.2 496 140c.1-26.2-16.3-47.9-38.3-57.2L269.4 2.9zM369 209L241 337c-9.4 9.4-24.6 9.4-33.9 0l-64-64c-9.4-9.4-9.4-24.6 0-33.9s24.6-9.4 33.9 0l47 47L335 175c9.4-9.4 24.6-9.4 33.9 0s9.4 24.6 0 33.9z"></path>
            </svg> Verified</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    mounted() {
        let intervalID = setInterval(this.updateFunction, 3000);
        // setTimeout(() => {
        //     // Clear the current setInterval timer
        //     clearInterval(intervalID);
            
        //     let times = Math.floor(Math.random() * 4000);

        //     // Set a new setInterval with the updated interval time
        //     intervalID = setInterval(this.updateFunction, times);

        //     console.log("Interval time changed to 2000 milliseconds.");
        // }, 5000); 
    },
    props: {
        ds: {
            type: Array,
            default: () => [
{ name: "Rethel", country: "🇳🇿 New Zealand", time: "1 day" },
{ name: "Quincey", country: "🇺🇸 United States", time: "7 hours" },
{ name: "Arney", country: "🇺🇸 United States", time: "1 day" },
{ name: "Chaim", country: "🇺🇸 United States", time: "17 hours" },
{ name: "Kevin", country: "🇩🇪 Germany", time: "22 hours" },
{ name: "Hugibert", country: "🇩🇪 Germany", time: "1 day" },
{ name: "Lazlo", country: "🇭🇺 Hungary", time: "1 hour" },
{ name: "Bibi", country: "🇬🇧 United Kingdom", time: "1 day" },
{ name: "Frederigo", country: "🇮🇹 Italy", time: "9 hours" },
{ name: "Kelwin", country: "🇬🇧 United Kingdom", time: "7 hours" },
{ name: "Jacquenette", country: "🇫🇷 France", time: "1 day" },
{ name: "Pippy", country: "🇺🇸 United States", time: "1 hour" },
{ name: "Caleb", country: "🇺🇸 United States", time: "2 days" },
{ name: "Adi", country: "🇫🇷 France", time: "1 day" },
{ name: "Cheryl", country: "🇺🇸 United States", time: "1 day" },
{ name: "Marvin", country: "🇺🇸 United States", time: "18 hours" },
{ name: "Sim", country: "🇬🇧 United Kingdom", time: "20 hours" },
{ name: "Paddie", country: "🇺🇸 United States", time: "1 hour" },
{ name: "Siward", country: "🇬🇧 United Kingdom", time: "1 hour" },
{ name: "Selia", country: "🇪🇸 Spain", time: "1 hour" },
{ name: "Filippo", country: "🇮🇹 Italy", time: "1 day" },
{ name: "Ryon", country: "🇺🇸 United States", time: "22 hours" },
{ name: "Tamra", country: "🇺🇸 United States", time: "20 hours" },
{ name: "Kylila", country: "🇺🇸 United States", time: "23 hours" },
{ name: "Fanya", country: "🇺🇸 United States", time: "12 hours" },
{ name: "Magdaia", country: "🇺🇸 United States", time: "1 day" },
{ name: "Biron", country: "🇬🇧 United Kingdom", time: "16 hours" },
{ name: "Gallagher", country: "🇮🇪 Ireland", time: "1 day" },
{ name: "Paulo", country: "🇧🇷 Brazil", time: "1 hour" },
{ name: "Zena", country: "🇬🇧 United Kingdom", time: "21 hours" },
{ name: "Cicely", country: "🇫🇷 France", time: "1 day" },
{ name: "Kippy", country: "🇺🇸 United States", time: "1 hour" },
{ name: "Brandyn", country: "🇺🇸 United States", time: "17 hours" },
{ name: "Cesar", country: "🇪🇸 Spain", time: "1 day" },
{ name: "Frank", country: "🇺🇸 United States", time: "1 day" },
{ name: "Cornelle", country: "🇫🇷 France", time: "1 hour" },
{ name: "Halette", country: "🇺🇸 United States", time: "2 days" },
{ name: "Bryana", country: "🇺🇸 United States", time: "1 hour" },
{ name: "Nelle", country: "🇺🇸 United States", time: "1 hour" },
{ name: "Lotty", country: "🇳🇿 New Zealand", time: "15 mins" },
{ name: "Sarajane", country: "🇺🇸 United States", time: "2 days" },
{ name: "Karlan", country: "🇺🇸 United States", time: "10 mins" },
{ name: "Kore", country: "🇺🇸 United States", time: "1 hour" },
{ name: "Leoine", country: "🇺🇸 United States", time: "21 hours" },
{ name: "Fernando", country: "🇧🇷 Brazil", time: "2 days" },
{ name: "Gussie", country: "🇳🇿 New Zealand", time: "1 hour" },
{ name: "Devan", country: "🇺🇸 United States", time: "1 day" },
{ name: "Chrissie", country: "🇺🇸 United States", time: "1 day" },
{ name: "Mariel", country: "🇺🇸 United States", time: "23 hours" },
{ name: "Joel", country: "🇺🇸 United States", time: "22 hours" },
{ name: "Marylinda", country: "🇺🇸 United States", time: "14 hours" },
{ name: "Leonelle", country: "🇳🇿 New Zealand", time: "12 hours" },
{ name: "Arabel", country: "🇺🇸 United States", time: "10 mins" },
{ name: "Dede", country: "🇺🇸 United States", time: "1 hour" },
{ name: "Ashbey", country: "🇺🇸 United States", time: "18 hours" },
{ name: "Eleanore", country: "🇪🇸 Spain" , time: "1 day" },
{ name: "Margery", country: "🇳🇿 New Zealand", time: "2 hours"},

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
        classname: "fixed absolute bottom-0 left-0 flex justify-center p-4 animate-move-up z-10",
        countryClass: "fi fi-round fi-de"
      };
    },
    methods: {
    //   startPopupTimer() {
    //     setInterval(this.updateFunction, 3000); // period of appear
    //   },
      updateFunction() {
        this.index = Math.floor(Math.random() * this.ds.length);
        this.countryClass = "fi fir fi-" + this.ds[this.index].icon;
        this.showPopup = !this.showPopup;
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