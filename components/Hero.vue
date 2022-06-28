<template>
    
    <div class="heading-wrapper">
      <h1 class="heading">
        <span class="intro">
            <span>scegli un</span>
        </span>
        <strong class="big-title">
          <span class="big-big-title">campione</span>
        </strong>
      </h1>
    </div>

</template>

<script>
export default {
    name: 'Hero',
}
</script>

<style lang="scss" scoped>
.heading-wrapper {
  position: relative;
  z-index: 1;
  text-align: center;
  color: white;
}
.heading {
  margin: 0px;
  font-weight: normal;
}
.intro {
    text-transform: uppercase;
    font-style: italic;
    line-height: 1.1;
    display: block;
    font-size: 1.5rem;
    line-height: 1;
    font-weight: 600;
    letter-spacing: 0.1em;
    @media (max-width: 599px) {
    font-size: 1rem;
  }
}
.big-title {
  text-transform: uppercase;
  font-style: italic;
  line-height: 1.1;
  display: block;
  font-size: 120px;
  line-height: 0.85;
  font-family: "BeaufortforLOL-Bold", sans-serif;
  font-weight: 800;
  letter-spacing: 0.03em;
  @media (max-width: 599px) {
    font-size: calc(22.24px + 4.3vw);
  }
  @media (min-width: 320px) {
    font-size: calc(22.24px + 4.3vw);
  }
}
.big-big-title {
  display: block;
  padding: 0px 15px 10px;
  margin-bottom: -10px;
}
</style>