<template>
  <div>
    <!-- Restaurant Profile Photo -->
    <div class="m-t-24 align-center" v-if="profileImage">
      <img :src="profileImage" class="w-64 h-64 r-64 cover" />
    </div>

    <!-- Restaurant Name -->
    <div class="m-t-8 align-center t-h6 c-text-black-high">{{ shopInfo.restaurantName }}</div>
  </div>
</template>

<script>
export default {
  props: {
    shopInfo: {
      type: Object,
      required: true
    }
  },
  computed: {
    profileImage() {
      return (
        (this.shopInfo?.images?.profile?.resizedImages || {})["600"] ||
        this.shopInfo.restProfilePhoto
      );
    }
  }
};
</script>
