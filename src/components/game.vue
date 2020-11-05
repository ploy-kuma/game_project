<template>
  <div>
      <div>
          <img src="http://assets.stickpng.com/thumbs/59c55df65c96ca0b1f994379.png" alt="">
      </div>
    <button @click="randomStart()" class="btn btn-danger btn-lg mb-2">Start</button>
    <div class="row">
      <div class="col">
        <button @click="randomDamage(1,20)" class="btn btn-primary mb-4">Attack</button>
        <button @click="randomDamageSP(50,80)" class="btn btn-info mb-4">SP Attack</button>
      </div>
    </div>
    <div class="container-fluid">
      <div class="row">
        <div class="col-3">
          <div class="btn btn-success" role="alert">Hero : {{randomPlayer}} HP : {{hp1}}</div>
          <img :src="image1" class="img-fluid" />
        </div>
        <div class="col-3">
          <div class="btn btn-success" role="alert">Monster : {{randomMonster}} HP : {{hp2}}</div>
          <img :src="image2" class="img-fluid" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      randomAttack: "1",
      randomSpAttack: "1",
      image1: "",
      image2: "",
      hp1: "",
      hp2: "",
      win: "https://stickershop.line-scdn.net/stickershop/v1/product/4066402/LINEStorePC/main.png;compress=true",
      lose: "https://i.pinimg.com/564x/68/cd/5f/68cd5f176c6335a2e4749f72c7dee306.jpg",
      player: [
        {
          name: "Cookie Run Ginger Brave",
          hp: 2000,
          image: "http://assets.stickpng.com/thumbs/59c55f5f5c96ca0b1f994397.png",
        },
        {
          name: "Cookie Run Ginger Brighte",
          hp: 1500,
          image:
            "http://assets.stickpng.com/thumbs/59c55f555c96ca0b1f994396.png",
        },
        {
          name: "Cookie Run Princess Cookie",
          hp: 1500,
          image: "http://assets.stickpng.com/thumbs/59c55e815c96ca0b1f994385.png",
        },
        {
          name: "Hero Cookie Run",
          hp: 2000,
          image: "http://assets.stickpng.com/thumbs/59c55f225c96ca0b1f994391.png",
        },
        {
          name: "Cookie Run Muay Thai",
          hp: 2000,
          image: "http://assets.stickpng.com/thumbs/59c55e725c96ca0b1f994384.png",
        },
        {
          name: "Strawberry Cookie Run",
          hp: 1800,
          image: "http://assets.stickpng.com/thumbs/59c55e945c96ca0b1f994387.png",
        },
        {
          name: "Snow Sugar Cookie Run",
          hp: 1800,
          image: "http://assets.stickpng.com/thumbs/59c55e2d5c96ca0b1f99437e.png",
        },
        {
          name: "Soda Cookie Cookie Run",
          hp: 1500,
          image: "http://assets.stickpng.com/thumbs/59c55eca5c96ca0b1f99438b.png",
        },
        {
          name: "Sea Fairy Cookie Run",
          hp: 2000,
          image: "http://assets.stickpng.com/thumbs/59c55f2a5c96ca0b1f994392.png",
        },
        
      ],
      randomPlayer: "",
      monster: [
        {
          name: "Cookie Run Devil Cookier",
          hp: 1500,
          image: "http://assets.stickpng.com/thumbs/59c55ee35c96ca0b1f99438d.png",
        },
        {
          name: "Cherry Cookie Run",
          hp: 1000,
          image: "http://assets.stickpng.com/thumbs/59c55e355c96ca0b1f99437f.png",
        },
        {
          name: "Fire Spirit Cookie Run",
          hp: 1800,
          image: "http://assets.stickpng.com/thumbs/59c55f1a5c96ca0b1f994390.png",
        },
        {
          name: "mZombie Cookie Run",
          hp: 1800,
          image: "http://assets.stickpng.com/thumbs/59c55dc55c96ca0b1f994376.png",
        },
        {
          name: "Special Force Cookie Run",
          hp: 1900,
          image: "http://assets.stickpng.com/thumbs/59c55e675c96ca0b1f994383.png",
        },
        {
          name: "Orange Cookie Run",
          hp: 1000,
          image: "http://assets.stickpng.com/thumbs/59c55e0d5c96ca0b1f99437b.png",
        },
      ],
      randomMonster: "",
    };
  },

  props: {
    Label: String,
  },

  methods: {
    randomStart: function () {
      var chosenNumber1 = Math.floor(Math.random() * this.player.length);
      this.randomPlayer = this.player[chosenNumber1].name;
      this.hp1 = this.player[chosenNumber1].hp;
      this.image1 = this.player[chosenNumber1].image;

      var chosenNumber2 = Math.floor(Math.random() * this.monster.length);
      this.randomMonster = this.monster[chosenNumber2].name;
      this.hp2 = this.monster[chosenNumber2].hp;
      this.image2 = this.monster[chosenNumber2].image;
    },

    randomDamage: function (min, max) {
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp1 -= this.randomAttack;
      }
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp2 -= this.randomAttack;
      }
      if (this.hp1 <= 0) {
        this.hp1 = 0;
        this.image1 = this.lose;
      }
      if (this.hp2 <= 0) {
        this.hp2 = 0;
        this.image2 = this.win;
      }
    },

    randomDamageSP: function (min, max) {
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp2 -= this.randomAttack;
      }
      if (this.hp1 <= 0) {
        this.hp1 = 0;
        this.image1 = this.lose;
      }
      if (this.hp2 <= 0) {
        this.hp2 = 0;
        this.image2 = this.win;
      }
    },
  },
};
</script>
