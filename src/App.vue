<script setup>
import { computed, reactive, ref } from "vue"

var qq = 1
let qq2 = 2
const count = ref(1)
const count2 = ref(2)
const count3 = computed(() => {
  // fefoijeoi
  return count.value * count2.value
})

const list = reactive([
  { id: 0, label: 'aa', value: 0, },
  { id: 1, label: 'bb', value: 0, },
  { id: 2, label: 'cc', value: 0, },
])

// function action () {
//   console.log('231')
// }

const action = (index) => {
  list[index].value++

  // if (count.value > 0) count.value++  
}

</script>

<template>
  <!-- <header>
    <Haha />
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
    

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header> -->

  <main>
    <!-- <TheWelcome /> -->
    <!-- <span>{{ list }}</span> -->
    <div v-for="(item, index) of list" :key="item.id">
      <span>{{ item.label }}: {{ item.value }}</span>
      <button @click="action(index)">add</button>
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
