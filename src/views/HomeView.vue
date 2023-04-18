<template>
  <div class="container mx-auto grid justify-items-center pt-[150px]">
    <h2 class="text-[64px] font-normal">Sign In</h2>
    <p class="primary-color font-normal leading-[20px]">Sign in and start managing your candidates!</p>
    <form class="grid max-w-[300px]">
      <input v-model="emailUser" class="primary-bg-color max-h-[45px] py-[12px] my-[32px] rounded-[10px] py-2 pl-9 pr-3 text-white placeholder-white text-[14px]" type="email" placeholder="Login" />
      <div v-if="errors && errors.emailUser" class="">{{errors.emailUser}}</div>
      <input v-model="passWordUser" class="primary-bg-color max-h-[45px] py-[12px] my-[32px] rounded-[10px] py-2 pl-9 pr-3 text-white placeholder-white text-[14px]" type="password" placeholder="Password" />
      <div class="flex items-center">
        <input class="primary-bg-color w-[18px] h-[18px] rounded-[5px] mr-[7px] " type="checkbox" /><label class="primary-color font-medium text-[14px] pr-[16px] " for="">Remember me</label>
         <a class="primary-color font-medium text-[14px] pl-[16px]" href="#">Forgot password?</a>
      </div>
      <button @click="onSubmit" type="submit" class="btn-color mt-[24px] py-[12px] rounded-[10px] primary-color font-normal">Login</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      emailUser: '',
      passWordUser:'',
      errors: null,
    }
  },
  methods: {
    // async submitForm() {
    //   const errors = {};
    //   if (!this.emailUser) {
    //     errors.emailUser = 'Email is required';
    //   } else if (!/^[^@]+@\w+(\.\w+)+\w$/.test(this.email)) {
    //     errors.emailUser = 'Invalid email';
    //   }

    //   if (Object.keys(errors).length > 0) {
    //     this.errors = errors;
    //     return;
    //   } else {
    //     this.errors = null;
    //   }

    //   // Handle submitting form
    // },
    onSubmit() {
      const errors = {};
      if (!this.emailUser) {
        errors.emailUser = 'Email is required';
      } else if (!/^[^@]+@\w+(\.\w+)+\w$/.test(this.email)) {
        errors.emailUser = 'Invalid email';
      }

      if (Object.keys(errors).length > 0) {
        this.errors = errors;
        
      // this.emailUser = '';
      // this.passWordUser = '';
        return;
      } else {
        console.log(this.emailUser,this.passWordUser)
        this.errors = null;
      }

      
      
    },
  }
}
</script>

<style lang="scss" scoped></style>
