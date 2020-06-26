<template>
  <Layout>
    <div class="container">
      <!-- Button goes selected province profile component. -->
      <transition name="bounce">
        <button
          v-show="province_name_for_profile"
          class="show-detail-button"
          @click="showProvinceDetail"
        >Detaylara bak</button>
      </transition>
      <!-- ------------------------------------------------ -->

      <!-- Turkey svg map component -->
      <turkey-map @provinceName="selected_province_name"></turkey-map>
      <!-- ----------------------- -->

      <!-- The component shows the selected province wiki page. -->
      <province-profile
        id="province-profile"
        v-show="province_name_for_profile"
        :provinceName="province_name_for_profile"
      ></province-profile>
      <!-- ---------------------------------------------------- -->
    </div>
  </Layout>
</template>

<script>
import turkeyMap from "../components/turkeyMap";
import provinceProfile from "../components/provinceProfile";
export default {
  metaInfo: {
    title: "Turkey Provinces"
  },
  components: { turkeyMap, provinceProfile },
  data() {
    return {
      province_name_for_profile: ""
    };
  },
  methods: {
    selected_province_name(val) {
      this.province_name_for_profile = val;
    },
    showProvinceDetail() {
      setTimeout(() => {
        var container = this.$el.querySelector("#province-profile");
        container.scrollIntoView({ behavior: "smooth", block: "end" });
      }, 500);
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: rgb(13, 6, 27);
}
.container > * {
  margin-top: 10px;
}
.description {
  width: 100%;
  background-color: #128576;
  color: white;
  text-align: center;
  padding: 10px 0;
  font-size: 1.5em;
}
#province-profile {
  overflow-y: auto;
}
.show-detail-button {
  cursor: pointer;
  width: 180px;
  height: 60px;
  line-height: 60px;
  font-size: 20px;
  font-weight: bold;
  border-radius: 12px;
  text-align: center;
  color: rgb(13, 6, 27);
  border: 2px solid white;
  box-sizing: content-box;
}
.bounce-enter-active {
  animation: bounce-in 0.5s;
}
.bounce-leave-active {
  animation: bounce-in 0.5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}
</style>
