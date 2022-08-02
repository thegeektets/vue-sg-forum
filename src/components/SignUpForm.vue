<template>
  <el-form
    ref="signUpFormRef"
    :model="signUpForm"
    status-icon
    :rules="rules"
    label-width="120px"
    class="sg-signup--form"
  >
    <el-form-item label="Name" prop="name">
      <el-input v-model="signUpForm.name" type="text" autocomplete="off" />
    </el-form-item>
    <el-form-item label="Email" prop="email">
      <el-input v-model="signUpForm.email" type="email" autocomplete="off" />
    </el-form-item>
    <el-form-item label="Password" prop="pass">
      <el-input v-model="signUpForm.pass" type="password" autocomplete="off" />
    </el-form-item>
    <el-form-item label="Confirm" prop="checkPass">
      <el-input
        v-model="signUpForm.checkPass"
        type="password"
        autocomplete="off"
      />
    </el-form-item>

    <el-form-item>
      <el-button type="primary" @click="submitForm(signUpFormRef)"
        >Submit</el-button
      >
      <el-button @click="resetForm(signUpFormRef)">Reset</el-button>
    </el-form-item>
  </el-form>
</template>

<script lang="ts" setup>
import { reactive, ref } from "vue";
import type { FormInstance } from "element-plus";

const signUpFormRef = ref<FormInstance>();

const signUpForm = reactive({
  name: "",
  pass: "",
  checkPass: "",
  email: "",
});

const submitForm = () => {
  console.log("submit!");
};
const resetForm = () => {};
</script>

<style scoped>
.sg-signup--form {
    padding-top: 20px;
    width: 50vw;
    margin: auto;
}
</style>