<template>
	<div class="baggage">
			<span>May stored value card?</span>
		<div style="display: flex; flex-direction: row-reverse; align-items: center;">
				<input type="checkbox" id="toggle" />
				<label for="toggle"></label>
				<div class="togglestatus" style="">
					<span style="color: transparent">[status]</span>
					<span class="false">Wala</span><!--
					--><span class="true">Meron</span>
				</div>
			</div>

	</div>
	
</template>

<style scoped>
div.baggage {
	padding: calc((2.8rem - 1.2rem)/ 2) 0.33em;
	border-radius: 8px;


	width: calc(92% - 2 * 0.33em);
	display: flex;
	justify-content: space-between;

	margin-top: 1.2rem;
	border: 1px solid #333333;
}

#toggle {
  display: none;
}

#toggle + label {
  display: inline-block;
  width: 2.25rem;
  height: 1.25rem;
  background-color: #ccc;
  border-radius: calc(1.25rem / 2);
  position: relative;
  cursor: pointer;
}

#toggle + label::before {
  content: "";
  position: absolute;
  top: 2px;
  left: 2px;
  width: calc(1.25rem - 4px);
  height: calc(1.25rem - 4px);
  background-color: white;
  border-radius: 50%;
  transition: transform 0.3s;
}

#toggle:checked + label {
  background-color: #172b1a;
}

#toggle:checked + label::before {
  transform: translateX(calc(2.25rem - 1.25rem));
}

#toggle + label + div > span.true, #toggle + label + div > span.false  {
  position: absolute;
}

#toggle + label + div {
  display: flex;
  justify-content: right;
  margin-right: 4px;
}

#toggle + label + div > span.false {
  color: gray;
  transition: color 0.3s ease-in;
}

#toggle:checked + label + div > span.false {
  color: transparent;
  transition: color 0.3s ease-in;
}

#toggle + label + div > span.true {
  color: transparent;
  transition: color 0.3s ease-in;
}

#toggle:checked + label + div > span.true {
  color: black;
  transition: color 0.3s ease-in;
}

div.togglecontainer {
  width: 85vw;
  margin-top: 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 18px 24px;
  box-sizing: border-box;
  border: 1px solid #172b1a;
  border-radius: 8px;
}

div.togglecontainer > span {
  color: black;
  font-weight: 600;
}

</style>