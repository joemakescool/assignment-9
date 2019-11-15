<template>
  <div class="container">
    <form>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->

          <!-- Full Name (First Name + Last Name) -->
          <FullName v-model="fullName"></FullName>


          <!-- Mail -->
          <label for="email">
            Email:
            <input
                    type="text"
                    id="email"
                    value="email"
                    v-model="email"
            >
          </label>
          <!-- Password -->
          <label for="password">
            Password:
            <input
                    type="text"
                    id="password"
                    value="password"
                    v-model="password"
            >
          </label>

          <!-- Store Data? Yes/No -->
          <label for="yes">
            YES
            <input
                    type="radio"
                    id="yes"
                    value=true
                    v-model="storeData"
            >
          </label>
          <label for="no">
            NO
            <input
                    type="radio"
                    id="no"
                    value=false
                    v-model="storeData"
            >
          </label>
          <hr>

          <!-- Exercise 2 -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->
          <button v-on:click.prevent="submitted(true)">Submit</button>


          <!-- Exercise 3 -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
        </div>
      </div>
    </form>
    <hr>
    <div class="row" v-if="isSubmitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ fullName }} </p>
            <p>Mail: {{ email }} </p>
            <p>Password: {{ password }} </p>
            <p>Store in Database?: {{ storeData }} </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

  import FullName from "@/components/FullName";

  export default {
    data: () =>({
      fullName: 'Joe Barker',
      email: '',
      password: '',
      storeData: false,
      isSubmitted: false
    }),

    methods: {
      submitted(isSubmitted){
        this.isSubmitted = isSubmitted
      }
    },

    components: {
      FullName
    }
  }
</script>

<style>
</style>
