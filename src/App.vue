<template>
  <router-view/>
</template>

<style lang="scss">

//@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,300;1,400;1,500;1,600;1,700;1,800&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');

*, ::after, ::before {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'TT Hoves', sans-serif;

  @font-face {
    font-family: "TT Hoves";
    src: local("TT Hoves"), url(./fonts/TThover/TTHoves-ExtraBold.ttf);
  }

}

html {
  font-size: 62.5%;
  background-repeat: repeat;
  overflow-x: hidden;
}

#app {
}

/*   SCROLL BAR   */
::-webkit-scrollbar-track {
  background-color: #F4F4F4;
}
::-webkit-scrollbar {
  width: 6px;
  background: #F4F4F4;
}
::-webkit-scrollbar-thumb {
  background: #dad7d7;
}

</style>
