<template>
  <Layout>
    <p class="description">{{description}}</p>
    <turkey-map @provinceName="province_name"></turkey-map>
    <province-profile :provinceName="province_name_for_profile"></province-profile>
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
      description:
        "Hakkında bilgi almak istediğiniz ili haritadan seçebilir ya da yukarıdan arama yapabilirsiniz.",
      province_name_for_profile: ""
    };
  },
  methods: {
    province_name(val) {
      this.province_name_for_profile = val;
    }
  }
};
</script>

<style>
.description {
  width: 100%;
  background-color: #128576;
  color: white;
  text-align: center;
  padding: 10px 0;
  font-size: 1.5em;
}
</style>
