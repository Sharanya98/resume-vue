<script setup>
import { ref } from 'vue'
import { PhotoIcon, UserCircleIcon } from '@heroicons/vue/24/solid'
import Personal from './Personal.vue';
import Skills from './Skills.vue';
import Build from './Build.vue';
import WorkExp from './WorkExp.vue';
import Home from './Home.vue';


const currentTab = ref('Personal')
const tabs = {

  Personal,
  WorkExp,
  Skills,
  Build
}





</script>

<template>
    <div class="flex flex-col items-center justify-center w-full mt-12 mb-12">
  <p class="text-3xl font-bold mb-14">OYESTER RESUME BUILDER</p>
  <div class="tabline">
    <button
  v-for="(_,tab) in tabs"
  :key="tab"
  :class="['tab-button', { active: currentTab === tab }]"
  @click="currentTab=tab">

  {{ tab }}
  </button>
  <component :is="tabs[currentTab]" class="tab"></component>

  </div>
  
 
</div>


 

 
 
</template>

<style scoped>
.tabline{

}
.tab-button {
  padding: 6px 10px;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
  border: 1px solid #ccc;
  cursor: pointer;
  background: #f0f0f0;
  margin-bottom: -1px;
  margin-right: -1px;
}
.tab-button:hover {
  background: #e0e0e0;
}
.tab-button.active {
  background: #e0e0e0;
}
.tab {
  border: 1px solid #ccc;
  padding: 10px;
}
</style>
