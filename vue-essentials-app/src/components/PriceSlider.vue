<template>
  <transition name="fade">
    <div v-if="sliderStatus">
      <div class="align-items-center" :class="sliderStatus">
        <label :class="labelArr" for="formMax">max</label>
        <input
          type="text"
          id="formMax"
          class="form-control mx-2"
          :style="{ width: inputWidth + 'px', textAlign: 'center' }"
          v-model="maximum"
        />
        <input
          type="range"
          class="custom-range"
          min="0"
          max="200"
          v-model="maximum"
        />
      </div>
    </div>
  </transition>
</template>

<script>

export default {
    name: 'PriceSlider',
    props: ['sliderStatus'],
    computed: {
        sliderStatus: function () {
            return this.sliderStatus ? "d-flex" : "d-none";
        }
    },
}
</script>

<style scoped>
.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 1s ease-in-out;
}
</style>