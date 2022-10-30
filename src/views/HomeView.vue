<template>
  <div class="container">
    <h1>Assine internet <br> 100% fibra <b>e pague só em 2023</b></h1>
    <figure>
      <img :src="require('../assets/background/homem_comemorando.png')" alt="homem_comemorando">
    </figure>
    <div class="plans">
      <img :src="require('../assets/background/items/480mbps.png')" alt="480mbps">
      <button>Quero 480Mb</button>
    </div>
    <div class="plans" style="top: -30%;">
      <img :src="require('../assets/background/items/740mbps.png')" alt="740mbps">
      <button>Quero 740Mb</button>
    </div>
    <div class="plans" style="top: -42%;">
      <img :src="require('../assets/background/items/1Gbps.png')" alt="1Gbps">
      <button>Quero 1Gb</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
}
</script>

<style scoped lang="scss">


.container {
  width: 100%;
  height: 100%;
  padding: 2% 30%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;

  h1 {
    color: #fb7411;
    font-size: 3.5rem;
    width: 55%;

    b {
      color: #fd341f;
    }
  }

  figure {
    position: relative;
    top: -7%;
    margin: 0 auto;
    img {
      position: relative;
      width: 25vw;
      height: auto;
      margin: 0 auto;
      display: block;
    }
  }

  .plans {
    position: relative;
    width: 100%;
    top: -20%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    img {
      width: 80%;
      height: auto;
      margin: 0 auto;
      display: block;
    }

    button {
      background: #fb7411;
      padding: 1rem 1.5rem;
      width: 40%;
      color: #ffffff;
      font-size: 2rem;
      font-weight: 800;
      border-radius: 20px;
      position: relative;
      top: -20%;
      border: 1px solid #fb7411;

      &:hover {
        border-color: #fb7411;
        background: #fff;
        color: #fb7411;
      }
    }
  }
}

</style>
