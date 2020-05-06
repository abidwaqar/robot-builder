<template>
  <div>
    <div class="top-row">
      <div class="top part">
        <img v-bind:src="availableparts.heads[headCounter].src" title="head" />
        <button class="prev-selector" v-on:click="decrementHeadCounter">&#9668;</button>
        <button class="next-selector" v-on:click="incrementHeadCounter">&#9658;</button>
      </div>
    </div>
    <div class="middle-row">
      <div class="left part">
        <img v-bind:src="availableparts.arms[leftArmCounter].src" title="right arm" />
        <button class="prev-selector" v-on:click="decrementLeftArmCounter">&#9650;</button>
        <button class="next-selector" v-on:click="incrementLeftArmCounter">&#9660;</button>
      </div>
      <div class="center part">
        <img v-bind:src="availableparts.torsos[torsoCounter].src" title="torso" />
        <button class="prev-selector" v-on:click="decrementTorsoCounter">&#9668;</button>
        <button class="next-selector" v-on:click="incrementTorsoCounter">&#9658;</button>
      </div>
      <div class="right part">
        <img v-bind:src="availableparts.arms[rightArmCounter].src" title="left arm" />
        <button class="prev-selector" v-on:click="decrementRightArmCounter">&#9650;</button>
        <button class="next-selector" v-on:click="incrementRightArmCounter">&#9660;</button>
      </div>
    </div>
    <div class="bottom-row">
      <div class="bottom part">
        <img v-bind:src="availableparts.bases[baseCounter].src" title="base" />
        <button class="prev-selector" v-on:click="decrementBaseCounter">&#9668;</button>
        <button class="next-selector" v-on:click="incrementBaseCounter">&#9658;</button>
      </div>
    </div>
  </div>
</template>

<script>
import availableparts from "../data/parts";

export default {
  name: "RobotBuilder",
  data() {
    return { availableparts, headCounter: 0, leftArmCounter: 0, rightArmCounter: 0, torsoCounter:0, baseCounter: 0 };
  },
  methods: {
    incrementHeadCounter: function(){
      if (this.headCounter != availableparts.heads.length - 1)
        this.headCounter += 1;
    },
    decrementHeadCounter: function(){
      if (this.headCounter != 0)
        this.headCounter -= 1;
    },
    incrementLeftArmCounter: function(){
      if (this.leftArmCounter != availableparts.arms.length - 1)
        this.leftArmCounter += 1;
    },
    decrementLeftArmCounter: function(){
      if (this.leftArmCounter != 0)
        this.leftArmCounter -= 1;
    },
    incrementRightArmCounter: function(){
      if (this.rightArmCounter != availableparts.arms.length - 1)
        this.rightArmCounter += 1;
    },
    decrementRightArmCounter: function(){
      if (this.rightArmCounter != 0)
        this.rightArmCounter -= 1;
    },
    incrementTorsoCounter: function(){
      if (this.torsoCounter != availableparts.torsos.length - 1)
        this.torsoCounter += 1;
    },
    decrementTorsoCounter: function(){
      if (this.torsoCounter != 0)
        this.torsoCounter -= 1;
    },
    incrementBaseCounter: function(){
      if (this.baseCounter != availableparts.bases.length - 1)
        this.baseCounter += 1;
    },
    decrementBaseCounter: function(){
      if (this.baseCounter != 0)
        this.baseCounter -= 1;
    }
  }
};
</script>

<style scoped>
.part {
  position: relative;
  width: 165px;
  height: 165px;
  border: 3px solid #aaa;
}
.part img {
  width: 165px;
}
.top-row {
  display: flex;
  justify-content: space-around;
}
.middle-row {
  display: flex;
  justify-content: center;
}
.bottom-row {
  display: flex;
  justify-content: space-around;
  border-top: none;
}
.head {
  border-bottom: none;
}
.left {
  border-right: none;
}
.right {
  border-left: none;
}
.left img {
  transform: rotate(-90deg);
}
.right img {
  transform: rotate(90deg);
}
.bottom {
  border-top: none;
}
.prev-selector {
  position: absolute;
  z-index: 1;
  top: -3px;
  left: -28px;
  width: 25px;
  height: 171px;
}
.next-selector {
  position: absolute;
  z-index: 1;
  top: -3px;
  right: -28px;
  width: 25px;
  height: 171px;
}
.center .prev-selector,
.center .next-selector {
  opacity: 0.8;
}
.left .prev-selector {
  top: -28px;
  left: -3px;
  width: 144px;
  height: 25px;
}
.left .next-selector {
  top: auto;
  bottom: -28px;
  left: -3px;
  width: 144px;
  height: 25px;
}
.right .prev-selector {
  top: -28px;
  left: 24px;
  width: 144px;
  height: 25px;
}
.right .next-selector {
  top: auto;
  bottom: -28px;
  left: 24px;
  width: 144px;
  height: 25px;
}
.right .next-selector {
  right: -3px;
}
</style>