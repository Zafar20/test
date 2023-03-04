<template>
  <div class="container">
    <div class="block__top">
      <div class="block__top-left">
        <div class="block__top-left-item" v-for="el in leftEl" :key="el.id">
          {{ el.name }}
        </div>
          <h4 class="title">{{ selected }}</h4>
      </div>
      <div class="block__top-right">
        <div class="block__top-right-item" v-if="rightEl">
          <h2>{{ rightEl.name }}</h2>
        </div>
      </div>
    </div>
    <div class="block__bottom">
      <div class="block__bottom-left">
        <div class="block__bottom-left-item" @click="blockLeft(el)" v-for="el in left" :key="el.id">
          <h2>{{ el.name }}</h2>
        </div>
      </div>
      <div class="block__bottom-right">
        <div class="block__bottom-right-item" @click="blockRight(el)" v-for="el in right" :key="el.id">
          <h2>{{ el.name }}</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'


let  left = ref([
              {"id": 1,"name": "Shoes 1"},
              {"id": 2,"name": "Shoes 2"},
              {"id": 3,"name": "Shoes 3"},
              {"id": 4,"name": "Shoes 4"},
              {"id": 5,"name": "T-shirt 1"},
              {"id": 6,"name": "T-shirt 2"},
              {"id": 7,"name": "T-shirt 3"},
              {"id": 8,"name": "T-shirt 4"},
            ])
let  right = ref([
              {"id": 11,"name": "Jacket 1"},
              {"id": 12,"name": "Jacket 2"},
              {"id": 13,"name": "Jacket 3"},
              {"id": 14,"name": "Jacket 4"},
              {"id": 15,"name": "Hoodie 1"},
              {"id": 16,"name": "Hoodie 2"},
              {"id": 17,"name": "Hoodie 3"},
              {"id": 18,"name": "Hoodie 4"},
            ])
   
    


let rightEl = ref(null)
let leftEl = ref([])


const selected = computed(() => `Selected ${leftEl.value.length} / 6`)

const blockRight = (el) => rightEl.value = el; 
const blockLeft = (el) => {
  if(leftEl.value.length < 6) {
    if(leftEl.value.includes(el)) {
      return 
    } 
    leftEl.value.push(el)
    
  }
}; 






</script>




