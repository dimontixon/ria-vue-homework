<template>
  <div>
    <Error />
    <form>
      <div class="row g-3">
        <div class="col-sm-5">
          <input type="text" class="form-control" placeholder="Your Name">
        </div>
        <div class="col-sm-5">
          <input type="text" class="form-control" placeholder="Your Email">
        </div>
        <div class="col-sm">
          <input type="text" class="form-control" placeholder="Your Age">
        </div>
      </div>
      <br>
      <div class="col">
        <button type="submit" class="btn btn-primary">Add User</button>
      </div>

    </form>
  </div>

</template>

<script>
import Error from "@/components/Error";
export default {
  name: "AddUser",
  components: {Error}
}
</script>

<style scoped>

</style>