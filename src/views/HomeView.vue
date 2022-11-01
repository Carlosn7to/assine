<template>
  <div class="container">
    <section :style="{ backgroundImage: 'url(' + require('@/assets/background/items/black_texture.png') + ')' }">
      <h1>Assine internet <br> 100% fibra <b>e pague <br> só em 2023</b></h1>
      <figure>
        <img :src="require('../assets/background/items/black_fibra.png')" alt="homem_comemorando">
      </figure>
      <div class="plans">
        <div class="plan">
          <img :src="require('../assets/background/items/89,50.png')" alt="480mbps">
          <a target="_blank" href="https://api.whatsapp.com/send/?phone=556140404040&text=Quero+contratar+480Mb+e+s%C3%B3+pagar+em+2023!">Quero 480Mb</a>
        </div>
        <div class="plan">
          <img :src="require('../assets/background/items/99,50.png')" alt="740mbps">
          <a target="_blank" href="https://api.whatsapp.com/send/?phone=556140404040&text=Quero+contratar+740Mb+e+s%C3%B3+pagar+em+2023!">Quero 740Mb</a>
        </div>
        <div class="plan">
          <img :src="require('../assets/background/items/159,50.png')" alt="1Gbps">
          <a target="_blank" href="https://api.whatsapp.com/send/?phone=556140404040&text=Quero+contratar+1Gb+Max+e+s%C3%B3+pagar+em+2023!">Quero 1Gb MAX</a>
        </div>
      </div>
      <div class="benefits">
        <span>Conheça as vantagens de ser AGE</span>
        <div class="items">
          <div class="item">
            <img :src="require('@/assets/background/items/SELO CLUBE DE VANTAGENS.png')" alt="clube_vantagens">
          </div>
          <div class="item">
            <img :src="require('@/assets/background/items/SELO HBO MAX.png')" alt="hbo_max">
          </div>
          <div class="item">
            <img :src="require('@/assets/background/items/SELO DEEZER.png')" alt="deezer">
          </div>
          <div class="item">
            <img :src="require('@/assets/background/items/SELO DR AGE.png')" alt="dr_age">
          </div>
        </div>
      </div>
    </section>
    <section :style="{ backgroundImage: 'url(' + require('@/assets/background/items/banner_2.png') + ')' }">
      <div class="description">
        <p>
          Escolha o plano de <br> Internet que mais <br> combina com o seu <br> estilo de vida e tenha <br>
          <b>ULTRAVELOCIDADE</b>
          <br>
          agora mesmo!
        </p>
      </div>
      <form action="#" @submit.prevent="postLead">
          <span>Quero começar a pagar <br> Internet só em 2023</span>
          <div class="inputs">
            <input type="text" name="name" id="name" placeholder="Nome" autocomplete="off" required v-model="payload.name">
            <input type="text" name="email" id="email" placeholder="Email" autocomplete="off" v-model="payload.email">
            <input type="text" name="telefone" id="telefone" placeholder="Telefone" autocomplete="off" required v-model="payload.tel">
          </div>
          <input type="submit" value="ENVIAR">
      </form>
    </section>
    <footer :style="{ backgroundImage: 'url(' + require('@/assets/background/items/banner_footer.png') + ')' }">
      <div class="content-footer">
        <h3>Conheça outras ofertas <br> em nossas redes</h3>
        <div class="socials">
          <a href="https://www.instagram.com/agetelecom/" target="_blank">
            <img :src="require('@/assets/background/items/INSTAGRAM.png')" alt="icone_instagram">
          </a>
          <a href="https://www.facebook.com/AgeTelecom" target="_blank">
            <img :src="require('@/assets/background/items/FACEBOOK.png')" alt="icone_facebook">
          </a>
          <a href="https://www.youtube.com/channel/UC10V9FvbHmdJgzf0QyLL9XQ/videos" target="_blank">
            <img :src="require('@/assets/background/items/YOUTUBE.png')" alt="icone_youtube">
          </a>
          <a href="https://api.whatsapp.com/send/?phone=556140404040&text=Quero+contratar+a+internet+Age+e+s%C3%B3+pagar+em+2023!" target="_blank">
            <img :src="require('@/assets/background/items/WHATS.png')" alt="icone_whattsapp">
          </a>
        </div>
        <p>
          Permanência mínima de 12 meses. Multa fidelidade de R$950,00 (pro rata),
          podendo também ser adquirido sem permanência mínima nos termos do regulamento.
          Pagamento em débito em conta disponível nos bancos Santander e Caixa Econômica Federal.
          Para correntistas dos demais bancos, os meios de pagamento disponíveis são apenas boleto e
          cartão de crédito (bandeiras Mastercard, Visa, Cielo, American Express, Elo, Diners Club, Agiplan,
          Banes Card, Hipercard, JCB, Credz). Sem taxa de instalação. Equipamentos em locação. Não é possível
          realizar downgrade nos 3 primeiros meses. Consulte disponibilidade dos serviços, valores, regulamento
          de ofertas, contrato de permanência e mais informações em: http://www.agetelecom.com.br.xn--ivg/
           Valores sujeitos a desconto de pontualidade.
        </p>
      </div>
      <div class="logo">
        <a href="https://www.agetelecom.com.br" target="_blank" ><img :src="require('@/assets/background/items/LOGO.png')" alt="logo_age"></a>
        <span>Conecte-se ao que te faz feliz.</span>
      </div>
    </footer>
  </div>
</template>

<script>


import axios from "axios";

export default {
  name: 'HomeView',
  data () {
    return {
      payload: {
        name: '',
        email: '',
        tel: ''
      },
      msg: null
    }
  },
  methods: {
    postLead: function () {
      axios({
        url: 'https://v1.ageportal.agetelecom.com.br/api/assine/leads',
        method: 'post',
        data: this.payload
      }).then((res) => {
        this.payload.name = ''
        this.payload.email = ''
        this.payload.tel = ''
        alert(res.data.msg)
      })
    }
  }
}


</script>

<style scoped lang="scss">


.container {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  background-color: #000;
  background-repeat: repeat;

  section:nth-child(1) {
    padding: 2% 15%;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    width: 100%;

    h1 {
      color: #fb7411;
      font-size: 3.5rem;
      width: 80%;
      font-weight: 800;
      margin-left: 15%;
      line-height: 3.6rem;

      b {
        color: #fd341f;
        font-weight: 800;
      }
    }

    figure {
      margin: 0 auto;
      img {
        position: relative;
        width: 40vw;
        margin: 0 auto;
        display: block;
        top: -5rem;

      }
    }

    .plans {
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      gap: 5vh;
      position: relative;
      top: -5rem;

      .plan {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 3vh;

        img {
          width: 100%;
          height: auto;
          margin: 0 auto;
          display: block;
        }

        a {
          background: #fb7411;
          padding: .8rem 1.5rem;
          width: 60%;
          color: #ffffff;
          font-size: 2rem;
          font-weight: 800;
          border-radius: 18px;
          border: 1px solid #fb7411;
          text-align: center;
          text-decoration: none;

          &:hover {
            border-color: #359f19;
            background-color: #359f19;
            color: #FFFFFF;
            cursor: pointer;
            transition: .2s ease;
          }

          &:active {
            background-color: #2b7b15;
            border-color: #2b7b15;
          }
        }
      }
    }

    .benefits {
      width: 100%;
      padding: 2vh 0 10vh 0;
      display: flex;
      align-items: center;
      flex-direction: column;
      gap: 2vh;

      span {
        color: #fb7411;
        font-weight: 800;
        font-size: 2rem;

      }

      .items {
        display: flex;
        align-items: center;
        gap: 1vw;
      }
    }
  }

  section:nth-child(2) {
    height: 50vh;
    background-position-x: 26vw;
    background-repeat: no-repeat;
    background-size: contain;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 3vw;

    .description {
      color: #fb7411;
      font-weight: 800;
      font-size: 2rem;

      b {
        color: #fd341f;
        font-weight: 800;

      }
    }

    form {
      position: relative;
      top: -3rem;
      width: 23vw;
      background-color:  #EF8600;
      border-radius: 15px;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 3vh 0vw;
      gap: 2vh;

      span {
        font-size: 1.8rem;
        color: #fff;
        font-weight: 800;
        text-align: center;
      }

      .inputs {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 2vh;
        input[type=text] {
          background-color: #ffffff;
          height: 7vh;
          border-radius: 5px;
          padding: 5px 2.5rem;
          border: none;
          width: 90%;
          outline: none;


          &:focus {
            border: none;
          }

        }
      }

      input[type=submit] {
        width: 90%;
        height: 7vh;
        border-radius: 5px;
        border: none;
        color: #fff;
        background-color: #EE3A29;
        transition: .2s ease;
        cursor: pointer;

        &:hover {
          background-color: #359f19;
        }
      }
    }
  }

  footer {
    width: 100%;
    background-size: contain;
    padding: 5% 15%;

    display: flex;
    align-items: center;
    gap: 8vw;

    .content-footer {
      display: flex;
      flex-direction: column;
      gap: 2vh;
      color: #FFFFFF;
      width: 60%;

      .socials {
        display: flex;
        gap: .5vw;
      }

      h3 {
        font-size: 2rem;
        font-weight: 800;
      }

      p {
        text-align: justify;
        font-size: 1.2rem;
      }
    }

    .logo {
      display: flex;
      flex-direction: column;
      width: 40%;
      gap: 2vh;
      img {
        width: 22vw;
        height: auto;
      }
      span {
        font-size: 1.8rem;
        color: #fff;
        font-weight: 800;
      }
    }

  }
}

@media (max-width: 1920px) {
  .container {

    section:nth-child(1) {

      h1 {
        font-size: 4rem;
        line-height: 4rem;
      }





    }
  }
}

</style>
