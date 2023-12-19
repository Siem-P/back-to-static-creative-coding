
  

<section class="container">
    <div class="sun"></div>
    <!-- <div class="sun"></div>  -->
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
        
       top: calc(40% - 10em);
       background-clip: border-box;

        /* Wont work because the image is loaded in through background-image */
        /* mix-blend-mode: color-burn; */ 
    }

    .sun::before, .sun::after {
        content: '';
        /* top: calc(25% + 11em); */
        transform: rotatex(180deg) translatey(15px); 
        mask-image: linear-gradient(transparent 70%, white 90%);

        border-radius: inherit;
        display: block;

    }

    .sun::before {
        background-image: linear-gradient(to top, rgba(220, 236, 5, 0.837), rgb(237, 237, 57)), url(/noise.png);
        
    }

    .sun::after {
        position: relative;
        width: inherit;
        height: 100%;
        background-image: inherit;
        top: 11em;
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

    
   
    div.wave:nth-of-type(2) {
        --wave-height: calc(100vh - 60%);
        --to-where: bottom
    }

    div.wave:nth-of-type(3) {
        --wave-height: calc(100vh - 97%);
    }
    div.wave:nth-of-type(4) {
        --wave-height: calc(100vh - 95%);
    }
    div.wave:nth-of-type(5) {
        --wave-height: calc(100vh - 93%);
    }
    div.wave:nth-of-type(6) {
        --wave-height: calc(100vh - 91%);
    }
    div.wave:nth-of-type(7) {
        --wave-height: calc(100vh - 88%);
    }

    div.wave:nth-of-type(8) {
        --wave-height: calc(100vh - 78%);
    }


</style>