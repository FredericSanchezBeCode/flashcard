<script>
	import { avatar } from './avatarData.js'
	export let name;
	let showName=False;
	const toggleShowName = () => showName = !showName;

	let avatarIndex = 0;
	$: image = avatar[avatarIndex].image;
	$: name = avatar[avatarIndex].name;

	const prev = () => {
		avatarIndex -= 1;
	}

	const next = () => {
		avatarIndex += 1;
	}
</script>


<div class="flip-card">
  <div class="flip-card-inner" class:flip-it={showName}>
    <div class="flip-card-front">
      <img src={image} alt={name} style="width:800px;height:800px;">
    </div>
    <div class="flip-card-back">
      <h1>{name}</h1> 
      <p>KELLER 2.24</p> 
      <p>8 mars 2021</p>
    </div>
  </div>
</div>

 <div id="btn-content">
	 <button on:click={prev}>-></button>;

	 <button on:click={toggleShowName}>{showName ? "Bambouzled" : "Switcherou"</button>;

	 <button on:click={next}><-</button>;
 </div>
<style>
		body {
		  font-family: Arial, Helvetica, sans-serif;
		}
		
		.flip-card {
		  background-color: transparent;
		  width: 800px;
		  height: 800px;
		  perspective: 1000px;
		}
		
		.flip-card-inner {
		  position: relative;
		  width: 100%;
		  height: 100%;
		  text-align: center;
		  transition: transform 0.6s;
		  transform-style: preserve-3d;
		  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
		}
		
		/* .flip-card:hover .flip-card-inner {
		  transform: rotateY(180deg);
		} */
		.flip-it {
		  transform: rotateY(180deg);
		}
		
		.flip-card-front, .flip-card-back {
		  position: absolute;
		  width: 100%;
		  height: 100%;
		  -webkit-backface-visibility: hidden;
		  backface-visibility: hidden;
		}
		
		.flip-card-front {
		  background-color: #bbb;
		  color: black;
		}
		
		.flip-card-back {
		  background-color: #2980b9;
		  color: white;
		  transform: rotateY(180deg);
		}
</style>