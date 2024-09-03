<template>
  <div class="semaphore">
    <div
        :class="`semaphore-red ${selectedColor === 'red' ? 'on' : 'off'}`"
        @click="setCor('red')"
    />
    <div
        :class="`semaphore-yellow ${selectedColor === 'yellow' ? 'on' : 'off'}`"
        @click="setCor('yellow')"
    />
    <div
        :class="`semaphore-green ${selectedColor === 'green' ? 'on' : 'off'}`"
        @click="setCor('green')"
    />
  </div>
</template>

<script setup>
import {ref} from 'vue';

const selectedColor = ref('red');

const setCor = (cor) => {
  selectedColor.value = cor;
};

</script>

<style scoped>
.semaphore {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.semaphore-red,
.semaphore-yellow,
.semaphore-green {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  cursor: pointer;
}

.semaphore-red {
  background-color: red;
}

.semaphore-yellow {
  background-color: yellow;
}

.semaphore-green {
  background-color: green;
}

.on{
  border: 2px solid white;
  opacity: 1;
}

.off{
  border: 2px solid transparent;
  opacity: 0.3;
}

</style>
