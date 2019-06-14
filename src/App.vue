<template>
  <div class="container">
    <form v-if="!formSubmitted">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">


          <!-- Exercise 3 -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
          <app-full-name v-model="fullName"></app-full-name>

          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->

          <div class="form-group">
            <label for="mail">Mail</label>
            <input type="text" class="form-control" id="mail" placeholder="Mail" v-model.lazy="mail">
          </div>

          <div class="form-group">
            <label for="password">Password</label>
            <input type="text" class="form-control" id="password" placeholder="Password" v-model.lazy="password">
          </div>

          <div class="form-group">
            <label for="">
              <input type="radio" name="store" value="yes" v-model="store">Yes
            </label>
            <label for="">
              <input type="radio" name="store" value="no" v-model="store">No
            </label>
          </div>


          <!-- Exercise 2 -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->

          <button type="submit" @click.prevent="formSubmitted = true" class="btn btn-primary">Submit the Form</button>



        </div>
      </div>
    </form>
    <hr>
    <div class="row" v-if="formSubmitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ fullName }}</p>
            <p>Mail: {{ mail }}</p>
            <p>Password: {{ password }}</p>
            <p>Store in Database?: {{ store }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import FullName from './FullName.vue'

  export default {
    data() {
      return {
        fullName: '   ',
        mail: '',
        password: '',
        store: 'yes',
        formSubmitted: false
      }
    },

    components: {
      appFullName: FullName
    }
  }
</script>

<style>
</style>
