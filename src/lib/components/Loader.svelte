<script>
    import { onMount } from "svelte";
    import Illuminati from "./Illuminati.svelte";

    let interactionColor

    onMount(() => {
        window.addEventListener("mousedown", function() {
            interactionColor = "fill: red"
        })

        window.addEventListener("mouseup", function() {
            interactionColor = "fill: black"
        })
    })
</script>


<section>
    <Illuminati fillColor={interactionColor} />
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

  transition: scale 2s cubic-bezier(0.88, -0.045, 0.305, 1);
  animation: rotate var(--speed, 1s) linear infinite;
}

/* On hover, the pre set scale is transitioned to. */
section:hover div {
  animation: rotate var(--speed, 1s) linear infinite;
  /* 		shrink 3s cubic-bezier(0.755, 0.050, 0.855, 0.060) 1; */
  animation-fill-mode: forwards;
  scale: 0.3;
}

@keyframes rotate {
  100% {
    rotate: 1turn;
  }
}

@keyframes shrink {
  100% {
    /* 		width:0em; */
    scale: 0.3;
  }
}

div::before,
div::after {
  content: "";
  width: 100%;
  height: 100%;
  display: block;

  border-radius: inherit;

  grid-column-start: 1;
  grid-row-start: 1;
}

div::before {
  background-image: conic-gradient(
    from -30deg,
    currentcolor 30deg,
    transparent 0
  );
  
  mask: radial-gradient(
    closest-side circle,
    transparent calc(100% - 0.2em),
    red 0
  );
}

div::after {
  position: absolute;

  width: 1em;
  height: 1em;
  background-color: currentcolor;

  top: calc(-0.5em + 0.1em);
}

div:nth-of-type(1) {
  color: green;
  --speed: 2s;
  --width: 16em;
}

div:nth-of-type(2) {
  --speed: 1.8s;
  --width: 13em;

  color: red;
}

div:nth-of-type(3) {
  --speed: 2.5s;
  --width: 18em;

  color: brown;
}

div:nth-of-type(4) {
  --speed: 3s;
  --width: 20em;

  color: hotpink;
}

div:nth-of-type(5) {
  --speed: 4s;
  --width: 23em;

  color: midnightblue;
}
div:nth-of-type(6) {
  --speed: 4.5s;
  --width: 25em;

  color: indianred;
}

div:nth-of-type(7) {
  --speed: 5s;
  --width: 27em;

  color: deeppink;
}

</style>