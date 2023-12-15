<script>
	import { onMount } from 'svelte';
	import Illuminati from './Illuminati.svelte';

	let interactionColor;

	onMount(() => {

        let allDivs = document.querySelectorAll('div')

       // give allDivs a class 
        allDivs.forEach(element => {
            element.classList.add('shrink')
        });
        
		window.addEventListener('mousedown', function () {
			interactionColor = 'fill: red'
            allDivs.forEach(element => {
                element.classList.add('shrink')
            });
            console.log(div)
		});

		window.addEventListener('mouseup', function () {
			interactionColor = 'fill: #eeebe3'
            
		});
	});
</script>

<section>
	<Illuminati fillColor={interactionColor || "fill: #eeebe3"} />
	<div></div>
	<div></div>
	<div></div>
	<div></div>
	<div></div>
	<div></div>
	<div></div>
    <div></div>
    <div></div>
    <div></div>
</section>

<style>
	section {
		display: grid;
		place-content: center;
		place-items: center;
		/* width: 30em; */
		height: 100%;
	}

	div {
		grid-column-start: 1;
		grid-row-start: 1;

		position: relative;

		width: var(--width, 15em);
		aspect-ratio: 1;

		background-color: #ffffff00;

		border-radius: 50%;

		display: grid;
		justify-items: center;

		
		animation: rotate var(--speed, 1s) linear infinite;
	}

    /* Class to use for interaction on mousedown */
    .shrink {
        animation-iteration-count: 1;
        animation: shrink 1s cubic-bezier(0.755, 0.050, 0.855, 0.060);
    }


	/* On hover, the pre set scale is transitioned to. */
	section:hover div {
		animation: rotate var(--speed, 1s) linear infinite;
	    animation: shrink 3s cubic-bezier(0.755, 0.050, 0.855, 0.060) 1;
		animation-fill-mode: forwards;
		
	}
    /* Rotate animation */
	@keyframes rotate {
		100% {
			rotate: 1turn;
		}
	}

    /* Gravitational ish animation */
	@keyframes shrink {
		100% {
			/* 		width:0em; */
			scale: 0.3;
		}
	}


    /* Create the styling for the single div's */
	div::before,
	div::after {
		content: '';
		width: 100%;
		height: 100%;
		display: block;

		border-radius: inherit;

		grid-column-start: 1;
		grid-row-start: 1;
	}

    /* Create the trail effect */
	div::before {
        
		background-image: conic-gradient(from var(--line-length-from, -30deg), transparent, currentcolor var(--line-length-to, 30deg), transparent 0);

		mask: radial-gradient(closest-side circle, transparent calc(100% - 0.3em), red 0);
	}

	div::after {
		position: absolute;

		width: 1em;
		height: 1em;
		background-color: currentcolor;

		top: calc(-0.5em + 0.2em);
	}


/* Editable properties from the div & trail length  */
/* 
        --speed - (from 0.5s to 10s) alter the speed of the orbit animation.
        --width - (from 12em to 30em) to alter distance between orbiting element and the center of the orbit.
        color - (can be any color) sets the color of the orb and trailing effect - 
    PS: make sure the color is in contrast to the background,
    
    The values from the two variables below must be the same number to keep te style functioning.
        --line-length-from (from -10deg to -60deg) has to include a '-', for example: '-30deg' 
        --line-length-to (from 10deg to 60deg) 
*/

	div:nth-of-type(1) {
		--speed: 2s;
		--width: 15em;

        color: green;
        
	}

	div:nth-of-type(2) {
		--speed: 1.8s;
		--width: 17em;

		color: red;

        --line-length-from: -40deg;
        --line-length-to: 40deg;
	}

	div:nth-of-type(3) {
		--speed: 2.5s;
		--width: 19em;

		color: brown;

	}

	div:nth-of-type(4) {
		--speed: 3s;
		--width: 21em;

		color: hotpink;

        --line-length-from: -45deg;
        --line-length-to: 45deg;
	}

	div:nth-of-type(5) {
		--speed: 4s;
		--width: 23em;

		color: rgb(36, 36, 152);
        --line-length-from: -40deg;
        --line-length-to: 40deg;
	}

	div:nth-of-type(6) {
		--speed: 4.5s;
		--width: 25em;

		color: indianred;

        --line-length-from: -45deg;
        --line-length-to: 45deg;
        
	}

	div:nth-of-type(7) {
		--speed: 5s;
		--width: 27em;

		color: deeppink;

        --line-length-from: -35deg;
        --line-length-to: 35deg;
	}

    div:nth-of-type(8) {
		--speed: 5.2s;
		--width: 29em;

		color: #26c485;

        --line-length-from: -40deg;
        --line-length-to: 40deg;
	}

    div:nth-of-type(9) {
		--speed: 6s;
		--width: 31em;

		color: #ff5964;

        --line-length-from: -45deg;
        --line-length-to: 45deg;
	}

    div:nth-of-type(10) {
		--speed: 5.7s;
		--width: 33em;

		color: #ffd639;

        --line-length-from: -30deg;
        --line-length-to: 30deg;
	}
</style>
