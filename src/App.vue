<template>
  <div id="app">
    <div class="row">
      <div class="option col-2">
        <div class="option__select">
          <select v-model="nowLayout" @change="initSolt()">
            <option v-for="option in layoutOption" :key="option">
              {{ option }}
            </option>
          </select>
        </div>
        <draggable
          v-model="myArray"
          :group="{
            name: 'test',
            pull: 'clone',
            put: false,
          }"
          :sort="false"
          :clone="(original) => original"
          class="option__box"
        >
          <div
            class="option__box__item"
            v-for="item in myArray"
            :key="item.name"
            :style="`background-color:${item.bgc}`"
          >
            {{ item.name }}
          </div>
        </draggable>
      </div>
      <div class="col-10 layout">
        <!-- 版型一 -->
        <div class="layout1" v-if="nowLayout == '版型一'">
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt1', e)"
            group="test"
            class="layout1__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt1?.bgc || '#fff'}`"
            >
              {{ solt.solt1?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt2', e)"
            group="test"
            class="layout1__solt"
            draggable="''"
            ><div :style="`background-color:${solt.solt2?.bgc || '#fff'}`">
              {{ solt.solt2?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt3', e)"
            group="test"
            class="layout1__solt"
            draggable="''"
            ><div :style="`background-color:${solt.solt3?.bgc || '#fff'}`">
              {{ solt.solt3?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt4', e)"
            group="test"
            class="layout1__solt"
            draggable="''"
          >
            <div :style="`background-color:${solt.solt4?.bgc || '#fff'}`">
              {{ solt.solt4?.name }}
            </div>
          </draggable>
        </div>
        <!-- 版型二 -->
        <div class="layout2" v-if="nowLayout == '版型二'">
          <draggable
            style="grid-area: solt1"
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt1', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt1?.bgc || '#fff'}`"
            >
              {{ solt.solt1?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt2', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt2?.bgc || '#fff'}`"
            >
              {{ solt.solt2?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt3', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt3?.bgc || '#fff'}`"
            >
              {{ solt.solt3?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt4', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt4?.bgc || '#fff'}`"
            >
              {{ solt.solt4?.name }}
            </div>
          </draggable>
        </div>
        <!-- 版型三 -->
        <div class="layout3" v-if="nowLayout == '版型三'">
          <draggable
            style="grid-area: solt1"
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt1', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt1?.bgc || '#fff'}`"
            >
              {{ solt.solt1?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt2', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt2?.bgc || '#fff'}`"
            >
              {{ solt.solt2?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt3', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt3?.bgc || '#fff'}`"
            >
              {{ solt.solt3?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt4', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt4?.bgc || '#fff'}`"
            >
              {{ solt.solt4?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt5', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt5?.bgc || '#fff'}`"
            >
              {{ solt.solt5?.name }}
            </div>
          </draggable>
          <draggable
            v-model="layoutContent"
            @change="(e) => layoutHandler('solt6', e)"
            group="test"
            class="layout2__solt"
            draggable="''"
          >
            <div
              slot="header"
              :style="`background-color:${solt.solt6?.bgc || '#fff'}`"
            >
              {{ solt.solt6?.name }}
            </div>
          </draggable>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable";
export default {
  name: "App",
  components: {
    draggable,
  },
  data() {
    return {
      myArray: [
        { name: "IM", bgc: "#faa" },
        { name: "DC", bgc: "#afa" },
        { name: "DR", bgc: "#aaf" },
        // { name: "LiceseHub", bgc: "#ddd" },
      ],
      layoutOption: ["版型一", "版型二", "版型三"],
      nowLayout: "版型一",
      layoutContent: [],
      solt: {
        solt1: {},
        solt2: {},
        solt3: {},
        solt4: {},
        solt5: {},
        solt6: {},
      },
    };
  },
  methods: {
    layoutHandler(target, event) {
      if (!event.added) return;
      for (let item in this.solt) {
        if (this.solt[item]?.name === event.added.element.name) {
          this.solt[item] = {};
        }
      }
      this.solt[target] = event.added.element;
      this.$forceUpdate();
    },
    initSolt() {
      for (let item in this.solt) {
        this.solt[item] = {};
      }
    },
  },
};
</script>

<style lang="scss" scoped>
#app {
  height: 90vh;
  width: 100%;
  overflow-x: hidden;
  .row {
    height: 100%;
    .option {
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    .layout {
      height: 100%;
      padding: 5vw !important;
      display: flex;
      align-items: center;
    }
  }
}
.option__select {
  display: flex;
  justify-content: center;
  margin-bottom: 40px;
  padding-left: 16px;
  select {
    width: 100%;
    padding: 16px 16px;
    font-size: 24px;
  }
}
.option__box {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-left: 16px;
  &__item {
    width: 100%;
    height: 90px;
    margin-bottom: 40px;
    border: 2px solid #000;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    cursor: pointer;
  }
}

.layout1 {
  height: 100%;
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  &__solt {
    width: 49%;
    height: 50%;
    border: 1px solid #000;
    position: relative;
    & > div {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
    }
  }
  .option__box__item {
    position: absolute;
    top: 0;
    left: 0;
    z-index: 5;
    height: 100%;
    background-color: #ddd;
  }
}
.layout2 {
  height: 100%;
  width: 100%;
  display: grid;
  grid-template-rows: 50% 50%;
  grid-template-columns: 33% 33% 33%;
  grid-template-areas:
    "solt1 solt1 solt1"
    "solt2 solt3 solt4";
  &__solt {
    width: 100%;
    height: 100%;
    border: 2px solid #000;
    position: relative;
    & > div {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
    }
    .option__box__item {
      position: absolute;
      top: 0;
      left: 0;
      z-index: 5;
      height: 100%;
      background-color: #ddd;
    }
  }
}

.layout3 {
  height: 100%;
  width: 100%;
  display: grid;
  grid-template-rows: 33% 33% 33%;
  grid-template-columns: 33% 33% 33%;
  grid-template-areas:
    "solt1 solt1 solt2"
    "solt1 solt1 solt3"
    "solt4 solt5 solt6";
  &__solt {
    width: 100%;
    height: 100%;
    border: 2px solid #000;
    position: relative;
    & > div {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
    }
    .option__box__item {
      position: absolute;
      top: 0;
      left: 0;
      z-index: 5;
      height: 100%;
      background-color: #ddd;
    }
  }
}
</style>
