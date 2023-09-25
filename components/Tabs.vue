<template>
	<ul>
    <li><span class="material-icons">directions_bus</span>EDSA<br/>Carousel</li>
    <li><span class="material-icons">tram</span>LRT-1</li>
    <li class="current"><span class="material-icons">tram</span>MRT-3</li>
    <li><span class="material-icons">tram</span>LRT-2</li>
	</ul>
</template>

<style scoped>
  /* Remove default styling */
  ul, li {
    margin: 0;
    padding: 0;
  }

  li {
    list-style: none;
  }

  /* Declare custom styling */
  ul {
    display: flex;
    font-size: 0.85rem;
    gap: 0.67rem;
    padding: 0 0.67rem;
  }

  li {
    width: 25%;
    display: flex;
    justify-content: center;
    align-items: center;

    padding: 0.5em 0;
    border-radius: 8px 8px 0 0;
  }

  li:first-child {
    font-size: 0.85em;
  }

  li:hover {
    cursor: pointer;
    background-color: #bbbbbb;
  }

  /* Highlight */
  li:not(.current) {
    border: 1px solid gray;
    border-bottom: none;
    margin-bottom: 2px;
  }
  
  li.current {
    border: 2px solid green;
    border-bottom: none;
    z-index: 1;
    background-color: white;
  }

  ul {
    box-shadow: 0 -2px 0 green inset;
  }

</style>
