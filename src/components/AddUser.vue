<template>
  <div>
    <Error
    :error="errorMessage"
    />
    <form>
      <div class="row g-3">
        <div class="col-sm-5">
          <input type="text" class="form-control" placeholder="Your Name" v-model="name">
        </div>
        <div class="col-sm-5">
          <input type="email" required="required" class="form-control" placeholder="Your Email" v-model="email">
        </div>
        <div class="col-sm">
          <input type="number" class="form-control" placeholder="Your Age" v-model="age">
        </div>
      </div>
      <br>
      <div class="col">
        <button type="submit" v-bind:class="buttonActive" class="btn btn-primary">Add User</button>
      </div>

    </form>
  </div>

</template>

<script>
import Error from "@/components/Error";
export default {
  name: "AddUser",
  components: {Error},
  data(){
    return{
      name: '',
      email: '',
      age: '',
      errorMessage: '',
      buttonActive: 'disabled'
    }
  },
  watch: {
    name(){
      if(this.name.length > 20 ) {
        this.errorMessage = 'Довжина поля name не може перевищувати 20 символів!';
        this.buttonActive = 'disabled';
        return;
      }else if(this.name.length < 1){
          this.errorMessage = 'Введіть ім\`я';
          this.buttonActive = 'disabled';
          return;
      }
      this.errorMessage = '';
      this.buttonActive = '';
    },
    age(){
      //this.errorMessage = this.age;
      if(this.age > 120 || this.age < 1) {
        if(this.age === ''){
          this.errorMessage = 'Введіть вік!';
          this.buttonActive = 'disabled';
          return;
        }
        this.errorMessage = 'Вік введено некоректно!'
        this.buttonActive = 'disabled';
        return;
      }

      this.errorMessage = '';
      this.buttonActive = '';

    },
  }
}
</script>

<style scoped>

</style>