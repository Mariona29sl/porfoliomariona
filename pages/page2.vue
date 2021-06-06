<template>
<div class="container4">
          <section class="panel blue">
            <b>ONE</b>
            <div class="blockFoto">
              <img class="radius" src="~/static/h1.png" alt="" />
              <img class="radius" src="~/static/h2.png" alt="" />
            </div>
          </section>
          <section class="panel turqoise">
            <b>TWO</b>
            <div class="blockFoto">
              <img class="radius" src="~/static/h3.png" alt="" />
              <img class="radius" src="~/static/h4.png" alt="" />
            </div>
          </section>
          <section class="panel green">
            <b>THREE</b>
            <div class="blockFoto">
              <img class="radius" src="~/static/h5.png" alt="" />
              <img class="radius" src="~/static/h6.png" alt="" />
            </div>
          </section>
          <section class="panel bordeaux">
            <b>FOUR</b>
            <div class="blockFoto">
              <img class="radius" src="~/static/h7.png" alt="" />
              <img class="radius" src="~/static/h8.png" alt="" />
            </div>
          </section>
        </div>
    
</template>

<script>
export default {
  mounted() { 

    //CONTAINER 4
    // init
   // var holi = new this.$scrollmagic.Scene();
   const controller2 = new this.$scrollmagic.Controller({
      globalSceneOptions: {
        triggerHook: "onLeave",
        duration: "200%", // this works just fine with duration 0 as well
        
        // However with large numbers (>20) of pinned sections display errors can occur so every section should be unpinned once it's covered by the next section.
        // Normally 100% would work for this, but here 200% is used, as Panel 3 is shown for more than 100% of scrollheight due to the pause.
      },
    })

    // get all slides
    var slides = document.querySelectorAll(".panel");
    var sceneprueba;
    // create scene for every slide
    for (var i = 0; i < slides.length; i++) {

        sceneprueba = new this.$scrollmagic.Scene({
        triggerElement: slides[i],
        })
        .setPin(slides[i], { pushFollowers: false })
         .addIndicators() // add indicators (requires plugin)
        .addTo(controller2);
    }



  }
}
</script>