<script setup lang="ts">
// import { defineComponent } from "@vue/composition-api";
import { ref, onMounted } from "vue";

// export default defineComponent({
//   setup() {},
// });
const periods = ["Today", "This Week", "This Month"];

let selectedPeriod = ref("today");

function selectePeriod(period: string) {
  selectedPeriod.value = period;
}

//username code

const username = ref("Denny");
function updateUsername(newUsername: any) {
  username.value = newUsername;
}
onMounted(() => {
  updateUsername("Steven");
});

//modal code

const isModalShown = ref(false);
function showModal() {
  isModalShown.value = true;
}
onMounted(() => {
  showModal();
});
</script>

<template>
  <div class="text-3xl font-bold rounded shadow w-screen h-11 bg-blue-400">
    {{ selectedPeriod }}
    <a
      v-for="period of periods"
      :key="period"
      class="
        items-center
        justify-center
        p-2
        text-base
        font-normal
        hover:text-slate-50
      "
      @click="selectePeriod(period)"
      :class="{ 'is-active': period === selectedPeriod }"
      >{{ period }}
    </a>
  </div>
</template>
<style scoped>
a.is-active {
  background: #fecdd3;
}
</style>

<!-- options API -->

<!-- <script>
export default {
    data() {
        return {
            username: 'Batul',
            isModalShown: false
        }
    }
},
methods: {
    updateUsername(newUsername){
        this.username =newUsername
    },
    showModal(){
        this.isModalShown = true
    }
},
mounted(){
    this.updateUsername('Steven')
    this.showModal()
}
</script> -->
