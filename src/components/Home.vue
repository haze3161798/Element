<template>
  <div class="container">
    <div>
      <div class="py-3">
        <h2>Check box &#38; Radio box</h2>
      </div>
      <div class="d-flex py-3">
        <div class="mx-2 d-flex align-items-center">
          <input class="radio-box-input" type="radio" name="flexRadioDefault" id="radio-box1" />
          <label class="radio-box-label position-relative" for="man"> </label>
          <label class="d-block px-2" for="radio-box1">radio-box1</label>
        </div>
        <div class="mx-2 d-flex align-items-center">
          <input class="radio-box-input" type="radio" name="flexRadioDefault" id="radio-box2" value="0" />
          <label class="radio-box-label position-relative" for="radio-box2"> </label>
          <label class="d-block px-2" for="radio-box2">radio-box2</label>
        </div>
        <div class="mx-2 d-flex align-items-center">
          <input class="radio-box-input" type="checkbox" id="check" value="0" />
          <label class="check-box-label position-relative" for="check"> </label>
          <label class="d-block px-2" for="check">check-box</label>
        </div>
      </div>
    </div>
    <div>
      <div class="py-3">
        <h2>各種按鈕</h2>
      </div>
      <div class="d-flex py-3">
        <!-- 按鈕1 -->
        <div class="px-2">
          <button type="button" class="demo-btn-1">
            <span class="position-relative" style="z-index: 1">按鈕1號 請停留三秒!</span>
          </button>
        </div>
        <!-- 按鈕2 -->
        <div class="px-2">
          <button type="button" class="demo-btn-2">
            <div class="demo-btn-2-size">
              <div class="d-flex justify-content-center">
                <div
                  v-for="(item, index) in btn2Array"
                  :key="item.id"
                  class="demo-btn-2-text"
                  :style="{ transition: `all linear 0.3s ${index * 20}ms` }"
                  v-html="item.text"
                ></div>
              </div>
              <div class="d-flex justify-content-center">
                <div
                  class="demo-btn-2-text"
                  v-for="(item, index) in btn2Array"
                  :key="item.id"
                  :style="{ transition: `all 0.8s ${index * 30}ms` }"
                  v-html="item.text"
                ></div>
              </div>
            </div>
          </button>
        </div>
        <!-- 按鈕3 -->
        <div class="px-2">
          <button class="demo-btn-3">
            <span>按鈕3號 Hover me!</span>
          </button>
        </div>
        <div class="px-2">
          <button class="demo-btn-4">按鈕4號 Hover me!</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      btn2String: '按鈕2號 Hover me!',
      delay: 0,
    }
  },

  computed: {
    btn2Array() {
      return this.btn2String.split('').map((p, i) => {
        if (p === ' ') {
          return {
            id: i,
            text: `<span style="display:inline-block;padding:0 2px;"></span>`,
          }
        }
        return {
          id: i,
          text: `<span>${p}</span>`,
        }
      })
    },
  },
}
</script>

<style>
.test {
  padding: auto;
}
</style>
