<template>
  <div>
    <el-form-item class="submit-form-item">
      <div class="submit-button__outer">
        <el-button class="submit-button" native-type="submit" :loading="loginLoading">
          <span class="submit-button__text">{{ loginTitle }}</span>
          <img src="@/assets/images/icons/chevron-icon.svg" alt="arrow" />
        </el-button>
      </div>
    </el-form-item>
    <el-form-item v-if="showSocial">
      <div class="or-text">or</div>
    </el-form-item>
    <el-form-item v-if="showSocial" class="submit-form-item">
      <el-button class="google-sign-button">
        <div class="google-sign-button__inner">
          <img src="@/assets/images/icons/google-icon.svg" alt="G" />
          <span class="google-sign-button__inner--text"
            >{{ socialTitle }}</span
          >
        </div>
      </el-button>
    </el-form-item>
  </div>
</template>

<script>
export default {
  name: 'LoginSubmitButtons',
  props: {
    loginTitle: {
        type: String,
        default: "",
    },
    socialTitle: {
        type: String,
        default: ""
    },
    showSocial: {
      type: Boolean,
      default: true
    },
    loginLoading: {
      type: Boolean,
      default: false,
    }
  },
}
</script>

<style scoped lang="scss">
.or-text {
  color: $ov-text--subtitle;
  display: flex;
  justify-content: center;
}
.submit-form-item {
  margin-bottom: 8px;
}
.google-sign-button {
  width: 100%;
  height: 48px;
  padding: 0;
  border-color: $ov-border--light;
  border-radius: 6px;
  box-shadow: 0px 7px 64px rgba(0, 0, 0, 0.07);
  &:focus,
  &:hover {
    background-color: white;
    border-color: $ov-primary;
  }
  &__inner {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 0 21px;
    color: black;
    font-size: 15px;
    font-weight: 500;
  }
}
.submit-button {
  background: linear-gradient(90.32deg, #0CB1B9 0.28%, #4156F6 99.75%);;
  color: white;
  text-transform: uppercase;
  width: 220px;
  height: 48px;
  padding: 0;
  padding-right: 8px;
  border-radius: 6px;
  ::v-deep span {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  &__text {
    width: 100%;
    display: flex;
    font-size: 17px;
    font-weight: 700;
    justify-content: center !important;
  }
  &__outer {
    display: flex;
    justify-content: center;
  }
}
</style>