<template>

  <div class="textlockup">
    <div class="img">
      <slot name="img">
        <img src="/banners/group_banner.jpg" alt="shoe" id="hero" />
      </slot>
    </div>
    <div class="new">
      <slot name="new">Shop Now</slot>
    </div>
    <div class="sale">
      <slot name="sale">Amp up your fitness this year
</slot>
    </div>
   <!-- <div class="collection">
      <slot name="collection">Collection</slot>
    </div>
    <div class="details">
      <slot name="details">Street Style New Fashion</slot>
    </div>-->
    <div class="collection">
      <slot name="collection">Shop the Amped Athlete range</slot>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.textlockup {
  display: grid;
  grid-template-columns: 50px 300px 100px 1fr 50px;
  grid-template-rows: 50px 260px 50px 50px;
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  .new {
    grid-area: 3 / 2 / 3 / 3;
    font-size: calc(min(max(16px, 2vw), 200px));
    color: #000000;
    font-family: "Montserrat";
    text-align: center;
    vertical-align: middle;
    font-weight: 700;
    text-transform: uppercase;
    border-width:2px; 
    border-style:solid; 
    border-color:#000000;
    background-color:#FFFFFFDD; 
  }
  .sale {
    grid-area: 2 / 2 / 3 / 4;
    font-size: calc(min(max(16px, 6.5vw), 60px));
    color: #000000;
    font-size: 40px;
    font-family: "Montserrat";
    font-weight: 700;
    text-transform: uppercase;
  }
  .collection {
    grid-area: 5 / 1 / 5 / 6;
    font-size: calc(min(max(16px, 8.5vw), 50px));
    font-family: "Montserrat";
    font-weight: 600;
    text-transform: uppercase;
    text-align:center;
    font-style:italic;
  }
  .details {
    grid-area: 4 / 2 / 5 / 4;
    font-size: calc(min(max(8px, 2vw), 25px));
    letter-spacing: 0.2em;
    text-transform: uppercase;
  }
  .img {
    grid-area: 1 / 1 / 5 / 6;
    #hero {
      width: 100%;
    height: 95%;
    object-fit: cover;
    object-position: 50% 60%;
    }
  }
}

@media screen and (max-width: 650px) {
  .textlockup {
    grid-template-columns: 25px 25px 1fr !important;
    grid-template-rows: 6vmin 5.5vmin 10vmin 20px 1fr !important;
  }
}
</style>