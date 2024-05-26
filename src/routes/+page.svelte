<script lang="ts">
	let color = $state('#ffffff');
	let rotation = $state(0);
	let boxShadow = $state(0);
	let height = $state(20);
	let width = $state(20);
	let x = $state(0);
	let y = $state(0);

	function handleColorChange(e: InputEvent) {
		const newColor = (e?.target as HTMLInputElement).value;

		color = newColor;
	}

	function handleRotationChange(e: InputEvent) {
		const newRotation = (e?.target as HTMLInputElement).value;
		rotation = parseInt(newRotation, 10);
	}

	function handleBoxShadowChange(e: InputEvent) {
		const newBoxShadow = (e?.target as HTMLInputElement).value;
		boxShadow = parseInt(newBoxShadow, 10);
	}

	function handleHeightChange(e: InputEvent) {
		const newHeight = (e?.target as HTMLInputElement).value;
		height = parseInt(newHeight, 10);
	}

	function handleWidthChange(e: InputEvent) {
		const newWidth = (e?.target as HTMLInputElement).value;
		width = parseInt(newWidth, 10);
	}

	function handleXChange(e: InputEvent) {
		const newX = (e?.target as HTMLInputElement).value;
		x = parseInt(newX, 10);
	}

	function handleYChange(e: InputEvent) {
		const newY = (e?.target as HTMLInputElement).value;
		y = parseInt(newY, 10);
	}
</script>

<div class="intro">
	<h1>Hi! My name is Koen, and this is my code project!</h1>
</div>

<section>
	<div class="documentary">
		<p>
			This is a project I made to learn about writing code! Code can be used to make websites,
			games, apps, and more! I'm learning how to write code so I can make cool things like that too!
		</p>

		<p>Here's some code that changes the color of the background!</p>

		<code> background-color: {color}; </code>

		<input type="color" on:input={handleColorChange} />
	</div>

	<div class="demo" style={`background-color: ${color}`}></div>
</section>

<section>
	<div class="documentary">
		<p>You can also write code to make things move! Here's some code that makes an image rotate!</p>

		<code> transform: rotate({rotation}deg); </code>
		<input type="range" value="0" min="0" max="360" on:input={handleRotationChange} />
	</div>

	<div class="demo">
		<img src="/fortnite.png" height="500" width="500" style={`transform: rotate(${rotation}deg)`} />
	</div>
</section>

<section>
	<div class="documentary">
		<p>Code can also make things look 3d! Here's some code that will add shadows to a circle</p>

		<code> box-shadow: {boxShadow}px 5px 10px; </code>
		<input type="range" value="0" min="0" max="360" on:input={handleBoxShadowChange} />
	</div>

	<div class="demo">
		<div class="circle" style={`box-shadow: 10px 5px ${boxShadow}px`} />
	</div>
</section>

<section>
	<div class="documentary">
		<p>Finally, code can make things move around the screen! Here's an example</p>

		<code> height: {height}px; </code>
		<code> width: {width}px; </code>
		<code> translateX: {x}px; </code>
		<code> translateY: {y}px; </code>

		<p>
			height: <input type="range" value="0" min="20" max="300" on:input={handleHeightChange} />
		</p>
		<p>
			width: <input type="range" value="0" min="0" max="360" on:input={handleWidthChange} />
		</p>
		<p>
			x: <input type="range" value="0" min="0" max="360" on:input={handleXChange} />
		</p>
		<p>
			y: <input type="range" value="0" min="0" max="360" on:input={handleYChange} />
		</p>
	</div>

	<div class="demo">
		<div
			class="square"
			style={`height: ${height}px; width: ${width}px; transform: translateX(${x}px) translateY(${y}px);`}
		/>
	</div>
</section>

<div class="intro">
	<h2>
		I hope you had fun learning about code with me! Now you can play with the settings by yourself
		or with a partner!
	</h2>
</div>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" />
	<link
		href="https://fonts.googleapis.com/css2?family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&family=Ubuntu+Sans:ital,wght@0,100..800;1,100..800&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<style>
	input {
		margin-top: 20px;
		border: 1px solid;
	}

	section {
		display: flex;
	}

	code {
		background-color: #000000;
		color: #ffffff;
		padding: 10px;
		flex: 1;
		display: block;
	}

	.intro {
		padding: 100px 20px;
		background-color: #40cdaa;
		text-align: center;
		font-family: 'Ubuntu Sans';
		color: white;
		font-size: 30px;
	}

	.demo {
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.documentary,
	.demo {
		padding: 20px;
		margin: 0;
		border: 1px solid;
		flex: 1;
		font-size: 25px;
	}

	.circle {
		width: 200px;
		height: 200px;
		background-color: #9841b6;
		border-radius: 50%;
		align-self: center;
		margin: 0 auto;
	}

	.square {
		height: 20px;
		width: 20px;
		align-self: center;
		justify-self: center;
		background-color: #c0ff33;
	}
</style>
