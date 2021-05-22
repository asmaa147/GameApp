<template>
  <div class="Login col-md-6 col-12 mx-auto py-4 my-4">
    <b-form>
      <h5 class="mb-3"> Please Add Your Account Details </h5>
      <b-form-group
        id="input-group-1"
        label="UserName / Email:"
        label-for="input-1"
      >
        <b-form-input
          id="input-1"
          type="email"
          placeholder="Type Your UserName Here"
          required
          class="my-3"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label="Passward:" label-for="input-2">
        <b-form-input
          id="input-2"
          type="passward"
          placeholder="Type Your Passward"
          required
          class="my-3"
        ></b-form-input>
      </b-form-group>
      <b-row>
        <span class="w-100 my-3"> Forget Passward ?</span>
      </b-row>
      <b-button
        type="submit"
        class="d-block m-auto my-3 px-4"
        style="background-color: #572589"
      >
        Login
      </b-button>
    </b-form>
  </div>
</template>

<script>
export default {
  name: "Login",
};
</script>
<style scoped>
.Login {
  position: absolute;
  background-color: #fff;
  height: fit-content;
  right: 3%;
  top: 50%;
  text-align: left;
  box-shadow: 0 4px 15px 5px rgba(0, 0, 0, 0.07);
}
.Login span {
  text-align: right;
  width: 100%;
}
</style>
