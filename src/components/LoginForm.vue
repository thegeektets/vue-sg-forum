<template>
  <el-form
    ref="loginFormRef"
    :model="loginForm"
    status-icon
    :rules="rules"
    label-width="120px"
    class="sg-signup--form"
  >
    <el-form-item label="Email" prop="email">
      <el-input v-model="loginForm.email" type="email" autocomplete="off" />
    </el-form-item>
    <el-form-item label="Password" prop="pass">
      <el-input v-model="loginForm.pass" type="password" autocomplete="off" />
    </el-form-item>
   
    <el-form-item>
      <el-button type="primary" @click="submitForm(loginFormRef)"
        >Submit</el-button
      >
      <el-button @click="resetForm(loginFormRef)">Reset</el-button>
    </el-form-item>
  </el-form>
</template>

<script lang="ts" setup>
import { reactive, ref } from "vue";
import type { FormInstance } from "element-plus";

const loginFormRef = ref<FormInstance>();

const loginForm = reactive({
  pass: "",
  email: "",
});

const submitForm = () => {
  console.log("submit!");
};
const resetForm = () => {};
</script>

<style scoped>
.sg-login--form {
    padding-top: 20px;
    width: 50vw;
    margin: auto;
}
</style>