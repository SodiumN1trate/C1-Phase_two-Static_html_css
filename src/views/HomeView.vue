<template>
  <main ref="background">
    <section>
      <div>
        <h1>"Stars in Graz"</h1>
        <h2>in 30.10.2021</h2>
        <div>
          <img src="/public/location-sharp.svg"><h2>Messe Congress Graz</h2>
        </div>
      </div>
        <h3>All information will be available in <strong>25.09.2021</strong></h3>
    </section>
  </main>
</template>

<script>
export default {
  data () {
    return {
      currentImage: 0,
      images: [
        'actionvance-eXVd7gDPO9A-unsplash.jpg',
        'aditya-chinchure-ZhQCZjr9fHo-unsplash.jpg',
        'anthony-delanoix-hzgs56Ze49s-unsplash.jpg',
        'austin-neill-hgO1wFPXl3I-unsplash.jpg',
        'Elton-John-Messe-Graz-Open-2560x1440.jpg',
        'filip-andrejevic-QmX5lw8StoQ-unsplash.jpg',
        'hanny-naibaho-aWXVxy8BSzc-unsplash.jpg',
        'marc-olivier-paquin-2_RQhbu0ZDQ-unsplash.jpg',
        'maxime-lebrun-h5G0WdtwcEg-unsplash.jpg',
        'roger-harris-Sj_FOinWBPI-unsplash.jpg',
        'sebastian-ervi-Qq2h76kYRFI-unsplash.jpg',
        'Volbeat-Special-Guests-2017-Messe-Graz-Freigelände-MCG-Wiesner-34-2560x1440.jpg',
        'yvette-de-wit-NYrVisodQ2M-unsplash.jpg',
      ]
    }
  },
  mounted () {
    this.$refs.background.style.backgroundImage = `url(/concert/${this.images[this.currentImage]})`
    this.currentImage++
    this.carousel()
  },
  methods: {
    carousel() {
      setTimeout(() => {
        this.$refs.background.style.backgroundImage = `url(/concert/${this.images[this.currentImage]})`
        this.currentImage++
        if (this.currentImage === 13) {
          this.currentImage = 0
        }
        this.carousel()
      }, 5000)
    }
  }
}
</script>

<style>
main {
    width: 100vw;
    height: 100vh;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    transition: .2s all;
    z-index: -1;
    position: relative;
    color: white !important;
}

main:before {
    position: absolute;
    content: '';
    background-color: rgba(26, 26, 26);
    width: 100vw;
    height: 100vh;
    z-index: 100;
    opacity: 0.65;
}

h1 {
    font-size: 135px;
    font-weight: bold;
    margin: 0;
    padding: 0;
}

h2 {
    font-size: 30px;
    font-weight: 500;
    margin: 0;
    padding: 0;
}


section {
    z-index: 101;
    display: flex;
    align-items: center;
    height: 100vh;
    width: 100%;
    flex-direction: column;
    justify-content: center;
    gap: 150px;
}

section > div {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}

section > div > div{
    display: flex;
    align-items: center;
    justify-content: center;
}

img {
    width: 35px;
    height: 25px;
}

@media screen and (max-width: 900px) {
    h1 {
        font-size: 70px;
    }
}
</style>
