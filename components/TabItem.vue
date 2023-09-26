<template>
  <li @click="clickTab" :class="{ current: props.code === route.path.substring(1) }">
    <span class="material-icons">{{props.icon}}</span><!--
    --><NuxtLink :to="props.code">{{props.label.replace(" ", "\n")}}</NuxtLink>
  </li>
</template>

<script setup>
  const props = defineProps(['label', 'icon', 'code']);
  const route = useRoute();

  const clickTab = () => {
    navigateTo(props.code);
  }
</script>

<style scoped>
  /* START Remove default styles */
  a {
    color: inherit;
    text-decoration: none;
  }

  li {
    margin: 0;
    padding: 0;
    list-style: none;
    transition: 0.5s;
  }
  /* END Remove default styles */

  /* BEGIN Declare custom styles */
  li {
    width: 25%;
    padding: 0.5em;

    display: flex;
    justify-content: center;
    align-items: center;

    border-radius: 8px 8px 0 0;
    border-style: solid;
    border-bottom: none;
  }
  li:first-child {
    font-size: 0.83em;
  }
  li:not(.current):hover {
    cursor: pointer;
    background-color: #bbbbbb;
  }
  
  a { white-space: pre-wrap; }
  li.current > a:hover { cursor: auto; }

  li.red > span { color: #e34234; }
  li.green > span { color: green; }
  li.yellow > span { color: #ffbf00;; }
  li.purple > span { color: purple; }
  /* END Declare custom styles */

  /* BEGIN Define dynamic attributes */
  li:not(.current) { 
    border-width: 1px;
    background-color: none;
    margin-bottom: 2px;
    border-color: gray;
  }

  li.current {
    border-width: 2px;
    background-color: white;
    margin-bottom: 0;
  }
  li.current.red { border-color: #e34234; }
  li.current.green { border-color: green; }
  li.current.yellow { border-color: #ffbf00; }
  li.current.purple { border-color: purple; }
  /* END Define dynamic attributes */
</style>
