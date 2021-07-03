<script lang="ts">
	import P5 from 'p5-svelte';

	const sketch = (p5) => {
		let t = 0;
		p5.setup = () => {
			p5.createCanvas(400, 400);
		}
		p5.draw = () => {
			p5.background(0);
			p5.fill(255);

			t += 0.01; // increment time by some small amount

			// map x to be within the range of the screen
			let x = p5.noise(t);
			x = p5.map(x, 0, 1, 0, p5.width);

			p5.ellipse(x, p5.width/2, 40, 40);
		}
	}
</script>

<center>
	<h1>Perlin Noise Demo</h1>
	<P5 {sketch}/>
</center>