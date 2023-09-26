<template>
	<ul :class="bordercolor">
    <TabItem label="EDSA Carousel" icon="directions_bus" 
      code="edsabus" class="red" />
    <TabItem label="LRT-1" icon="tram" code="lrt1" class="green" />
    <TabItem label="MRT-3" icon="tram" code="mrt3" class="yellow" />
    <TabItem label="LRT-2" icon="tram" code="lrt2" class="purple" />
	</ul>
</template>

<script setup>
  const route = useRoute();

  const bordercolor = computed(() => ({
    'red': route.path.substring(1) === "edsabus",
    'green': route.path.substring(1) === "lrt1",
    'yellow': route.path.substring(1) === "mrt3",
    'purple': route.path.substring(1) === "lrt2"
  }))
</script>

<style scoped>
  /* Remove default styles */
  ul { 
    margin: 0;
    padding: 0;
  }

  /* Declare custom style */
  ul {
    display: flex;
    font-size: 0.67rem;
    gap: 4px;
    padding: 0 0.33rem;
    overflow-x: scroll;
  }

  /* Dynamic border */
  ul { box-shadow: 0 -2px 0 black inset; }
  ul.red { box-shadow: 0 -2px 0 #e34234 inset; }
  ul.green { box-shadow: 0 -2px 0 green inset; }
  ul.yellow { box-shadow: 0 -2px 0 #ffbf00 inset; }
  ul.purple { box-shadow: 0 -2px 0 purple inset; }
</style>