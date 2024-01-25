<template>
  <Image src="./assets/Astronout-BW.jpg" idName="bg-wallpaper" />
  <h2>WELCOME</h2>
  <p>IN <span>AEROSPACES</span></p>

  <div id="buttonContainer">
    <Buttons idName="register" text="REGISTER" @btnClick="toggleRegister" />
    <Buttons idName="info" text="INFO" @btnClick="toggleInfo" />
  </div>

  <Modal :className="showModalInfo ? 'show' : 'close'" @close="toggleInfo">
    <Image
      src="./assets/Astronout-Inspace.png"
      alt="Astronaut"
      idName="astronaut-ovw"
    />
    <div class="modalBody">
      <p>
        Once upon a time, in the not-so-distant future, humanity had set its
        sights on the stars. A group of courageous individuals, known as
        astronauts, were at the forefront of this celestial exploration. Among
        them was Captain Emma Mitchell, a seasoned spacefarer with a heart full
        of curiosity and a mind determined to unravel the mysteries of the
        universe. Emma had always been fascinated by the cosmos. As a child, she
        would gaze up at the night sky, wondering what secrets lay beyond the
        twinkling stars. This passion led her to pursue a career in
        astrophysics, and eventually, she became one of the select few chosen to
        venture into the great unknown. In this future era, Earth had
        established a bustling space agency, collaborating with nations around
        the globe to push the boundaries of human exploration. The International
        Space Exploration Alliance, or ISEA, was the epicenter of these efforts.
        Their missions extended beyond the Moon, reaching distant planets,
        moons, and even other star systems. Emma was selected for a
        groundbreaking mission to explore a distant exoplanet, Kepler-452b,
        which exhibited promising signs of habitability. The journey required an
        advanced spacecraft, the Stellar Voyager, equipped with cutting-edge
        technology and an international crew of scientists, engineers, and, of
        course, astronauts. The day of the launch arrived, and the world watched
        with bated breath as the Stellar Voyager soared into the cosmos. For
        Emma and her crewmates, the journey was a mix of excitement and
        anticipation. They spent months traversing the vastness of space, their
        ship hurtling through the cosmic expanse at mind-boggling speeds. As the
        Stellar Voyager approached Kepler-452b, the astronauts marveled at the
        alien beauty of the exoplanet. Its landscapes were unlike anything they
        had ever seen – towering mountains, vast oceans, and skies painted in
        hues beyond earthly imagination. The astronauts conducted experiments,
        gathered data, and explored the newfound world. Their discoveries were
        awe-inspiring, providing valuable insights into the potential for life
        beyond Earth. Emma, in particular, reveled in the thrill of exploration,
        embracing the challenges and marveling at the wonders of the universe.
        However, their mission wasn't without peril. A sudden solar storm
        threatened the safety of the Stellar Voyager, and the astronauts had to
        work together to navigate through the celestial turbulence. Their
        training, teamwork, and resilience proved crucial, and they emerged from
        the storm unscathed, a testament to the indomitable spirit of
        astronauts. As the crew prepared to return home, their hearts were
        filled with a profound sense of accomplishment. The journey had been a
        testament to human ingenuity, the unquenchable thirst for knowledge, and
        the courage to venture into the unknown. And so, Captain Emma Mitchell
        and her crew re-entered Earth's atmosphere, bringing with them the
        knowledge and inspiration that would shape the future of space
        exploration. The story of astronauts, those intrepid explorers who dared
        to journey beyond the confines of our world, continued to inspire
        generations to come, igniting the flames of curiosity and paving the way
        for humanity's ongoing quest to unravel the mysteries of the cosmos.
      </p>
    </div>
  </Modal>

  <Modal
    :className="showModalRegister ? 'show' : 'close'"
    @close="toggleRegister"
    idName="formModal"
  >
    <Forms />
  </Modal>
</template>

<script>
import Image from './components/Image.vue';
import Buttons from './components/Buttons.vue';
import Modal from './components/Modal.vue';
import Forms from './components/Forms.vue';

export default {
  name: 'App',
  components: {
    Image,
    Buttons,
    Modal,
    Forms,
  },
  data() {
    return {
      showModalInfo: false,
      showModalRegister: false,
    };
  },
  methods: {
    toggleInfo() {
      this.showModalInfo = !this.showModalInfo;
    },
    toggleRegister() {
      this.showModalRegister = !this.showModalRegister;
    },
  },
};
</script>

<style>
body {
  background-color: black;
  width: 100vw;
  overflow-x: hidden;
  color: rgb(169, 169, 169);
  font-family: 'Courier New', Courier, monospace;
}

* {
  z-index: 2;
  padding: 0;
  margin: 0;
}

#app {
  width: 100vw;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

#bg-wallpaper {
  position: absolute;
  z-index: -1;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  opacity: 0.5;
}

h2 {
  font-size: 5vw;
  text-align: center;
}

p {
  font-size: 2vw;
}

span {
  color: rgb(255, 255, 255);
  font-weight: bolder;
}

#buttonContainer {
  margin-top: 2%;
  width: 250px;
  height: auto;
  display: flex;
  justify-content: space-around;
}

#astronaut-ovw {
  position: absolute;
  width: 30%;
  height: 100%;
  opacity: 0.5;
}

.modalBody {
  width: 60%;
  height: 100%;
  display: flex;
  align-items: center;
}

.modalBody p {
  font-size: 12px;
  /* color: #ff14dc; */
  color: #a5a5a5;
  text-align: justify;
  font-weight: bold;
}

#formModal {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
