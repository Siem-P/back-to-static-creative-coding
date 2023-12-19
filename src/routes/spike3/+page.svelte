
  

<section class="container">
    <div class="sun"></div>
    <div class="wave"></div>
    <div class="wave"></div>
    <div class="wave"></div>
    <div class="wave"></div>
    <div class="wave"></div>
    <div class="wave"></div>
    <div class="wave"></div>
</section>


<style>
    section {
        display: flex;
        flex-direction: column;
        /* justify-content: center; */
        align-items: center;
        /* background-image: url(./noise.png); */
        background-size: 100%;
        width: 100%;
        height: 100vh;
        position: relative;
        overflow: hidden;
    }


    .sun {
        /* display: flex; */
       
        position: absolute;
        aspect-ratio: 1;        
        
        background-image: linear-gradient(to top, rgba(220, 236, 5, 0.837), rgb(237, 237, 57)), url(/noise.png);
        background-size: cover, contain;
        background-position: center, right bottom;
        background-repeat: no-repeat, no-repeat;
        background-blend-mode: color-burn;

        border-radius: 50%;
        width: 10em;
        
       top: 30%;

        /* Wont work because the image is loaded in through background-image */
        /* mix-blend-mode: color-burn; */

        
    }

    .wave {
        display: flex;
        background-image: linear-gradient(to var(--to-where, top), rgb(4, 208, 253), rgb(97, 255, 252) 60%), url(/noise.png);
        background-size: cover, contain;
        background-position: center, right bottom;
        background-blend-mode: color-burn;
        
        width: 100%;
        height: var(--wave-height, 5em);
    }

   
    div:nth-of-type(2) {
        --wave-height: 28em;
        --to-where: bottom
    }

    div.wave:nth-of-type(3) {
        --wave-height: 3.5em;
    }

    div:nth-of-type(4) {
        --wave-height: 4.5em;
    }
    div:nth-of-type(5) {
        --wave-height: 5.5em;
    }
    div:nth-of-type(6) {
        --wave-height:  6.5em;
    }
    div:nth-of-type(7) {
        --wave-height: 9em;
    }

    div:nth-of-type(8) {
        --wave-height: 11em;
    }


</style>