<template>
  <Layout>
    <div class="container">
      <!-- Button goes selected province profile component. -->
      <button
        v-show="province_name_for_profile"
        class="show-detail-button"
        @click="showProvinceDetail"
      >Detaylara bak</button>
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
  width: 140px;
  height: 60px;
  font-size: 20px;
  background-color: rgb(13, 6, 27);
  border-radius: 12px;
  color: white;
  box-sizing: content-box;
}
</style>
