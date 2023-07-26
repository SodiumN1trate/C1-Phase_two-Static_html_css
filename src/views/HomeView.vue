<template>
  <main>
    <nav>
      <a href="#schedule" style="cursor: pointer">Schedule</a>
      <a href="#Purchase" style="cursor: pointer">Tickets</a>
      <a href="#Testimonial" style="cursor: pointer">Testimonial</a>
      <a href="#Frequently" style="cursor: pointer">FaQ</a>
    </nav>
    <header class="landing" ref="background">
      <section>
        <div>
          <h1>"Stars in Graz"</h1>
          <h2>in 30.10.2021</h2>
          <div>
            <img src="/public/location-sharp.svg"><h2>Messe Congress Graz</h2>
          </div>
          <br>
          <p style="width: 40vw; text-align: center">Messe Congrez Graz is the largest multi-functional event hall in Graz.
            Even before Stars in Graz, the location featured many international bands and musicians.
            Be a part of it and experience the unique atmosphere during a very special evening.</p>
        </div>
        <!--        <h3>All information will be available in <strong>25.09.2021</strong></h3>-->
      </section>
    </header>
    <div id="schedule" class="section">
      <h1>Concert schedule</h1>
      <hr>
      <ul>
        <li>17:00 Bilderbuch</li>
        <li>18:00 Wanda</li>
        <li>19:00 Christina Stürmer</li>
        <li>20:00 Volbeat</li>
        <li>21:00 Imagine Dragons</li>
        <li>22:00 Opus</li>
      </ul>
    </div>
    <div id="Purchase" class="section">
      <h1>Purchase tickets online</h1>
      <hr>
      <button class="buy-ticket">Buy tickets</button>
    </div>
    <div id="Testimonial" class="section">
      <h1>Testimonial</h1>
      <hr>
      <div class="card">
        <h2>Bill Deasy</h2>
        <p>The Stars in Graz Experience was nothing short of amazing.
          The joy from the stage was infectious.
          In all my years of booking concerts, none has caused a more emphatically enthusiastic response.
          It was off the charts!</p>
      </div>
      <div class="card">
        <h2>Mark Lipman</h2>
        <p>Time stood still at last night's concert... Thanks so much! We had a fab time!</p>
      </div>
    </div>
    <div id="Frequently" class="section">
      <h1>Frequently asked question</h1>
      <hr>
      <div class="card">
        <h2>What is Stars in Graz?</h2>
        <p>Stars in Graz is a one-day music concert where many different artists perform their most popular songs.
          It takes place once a year since 2015.</p>
      </div>
      <div class="card">
        <h2>When does Stars in Graz take place?</h2>
        <p>On 30.10.2021.
          The first act starts at 17:00.</p>
      </div>
      <div class="card">
        <h2>What is the age minimum?</h2>
        <p>Persons under 16 years of age are not allowed to enter without the accompaniment of an adult.</p>
      </div>
      <div class="card">
        <h2>Can I pay by credit card?</h2>
        <p>Yes, credit cards can be used at all food stands.</p>
      </div>
      <div class="card">
        <h2>What is the golden circle?</h2>
        <p>In the Golden Circle, you experience your favorite act as close as possible.
          It is located directly in front of the stage.
          Show your Golden Circle ticket and you'll get to this area quickly and easily thanks to a separate entrance.</p>
      </div>
      <div class="card">
        <h2>Are there wheelchair spaces?</h2>
        <p>Of course, wheelchair spaces are available.
          However, spaces are limited. Please contact us in advance for more information.</p>
      </div>
      <div class="card">
        <h2>Can I resale my ticket if I cannot go?</h2>
        <p>The resale of the tickets is prohibited.
          For security reasons, we also strongly advise against buying the tickets from anyone.
          Anyone who tries to gain access to the event with copied or forged tickets will be suspected of ticket misuse and prosecuted.</p>
      </div>
    </div>
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
html, body {
    scroll-behavior: smooth;
}

nav {
    background-color: #181818;
    height: 50px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: start;
    padding-left: 200px;
    gap: 50px;
    scroll-behavior: smooth;
}

nav > a {
    color: white;
    font-size: 18px;
    font-weight: 600;
    scroll-behavior: smooth;
}

main {
    min-width: 99.2vw;
    scroll-behavior: smooth;
}
.landing {
    width: 100%;
    min-height: 100vh;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    transition: .2s all;
    z-index: -1;
    position: relative;
    color: white !important;
    scroll-behavior: smooth;
}

.landing:before {
    position: absolute;
    content: '';
    background-color: rgba(26, 26, 26);
    height: 100vh;
    z-index: 1;
    overflow-x: hidden;
    width: 100%;
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
    z-index: 2;
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

.section {
    display: flex;
    align-items: center;
    justify-content: stretch;
    margin-top: 150px;
    flex-direction: column;
    gap: 10px;
}

.section > h1 {
    font-size: 50px;
}

.section > ul > li {
    font-size: 24px;
}

.buy-ticket {
    font-size: 32px;
    padding: 16px;
    color: white;
    background-color: #282828;
    outline: none;
    border: none;
    border-radius: 10px;
    z-index: 200;
    cursor: pointer;

}

.card {
    max-width: 550px;
    border: 1px solid #f1f1f1;
    padding: 16px;
    border-radius: 20px;
}

@media screen and (max-width: 1100px) {
    .card {
        width: 350px;
    }
    main {
        min-width: 97vw;
        scroll-behavior: smooth;
    }
    nav, .section {
        padding: 0;
        justify-content: center;
        align-items: center;
        text-align: center;
    }
    h1 {
        font-size: 60px;
    }
}
</style>
