<template>
  <a :href="href">{{ content }}</a>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  href: String,
  content: String,
});
</script>

<style scoped>
a {
  color: var(--secondary-color);
  font-family: 'Karantina';
  text-decoration: none;
  font-size: 4rem;
  position: relative;
}

a::before {
  content: '';
  height: 4px;
  width: 0;
  position: absolute;
  bottom: 0;
  background-color: var(--secondary-color);

  transition: width 0.1s ease-in-out;
}
a:hover {
  cursor: pointer;
}

a:hover::before {
  width: 100%;
}

@media only screen and (max-width: 650px) {
  a {
    background-color: var(--bg-color);
    padding: 0.4rem 1rem;
    width: 90%;
    text-align: center;
    border-radius: 0.4rem;
  }
}
</style>
