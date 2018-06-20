<template>
    <div class="container">
        <div v-if="!submited" class="row">
            <form>
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>Sign Up Form</h1>
                    <hr>

                    <div class="form-group">
                        <label for="firstname"> First Name</label>
                        <input 
                            type="text" 
                            id="firstname" 
                            class="form-control"
                            v-model="userData.firstName">
                    </div>
                    
                    <div class="form-group">
                        <label for="lastname"> Last Name</label>
                        <input 
                            type="text" 
                            id="lastname" 
                            class="form-control"
                            v-model="userData.lastName">
                    </div>

                    <div class="form-group">
                        <label for="email">Mail</label>
                        <input
                                type="text"
                                id="email"
                                class="form-control"
                                v-model="userData.email">
                    </div>

                    <div class="form-group">
                        <label for="password">Password</label>
                        <input
                                type="password"
                                id="password"
                                class="form-control"
                                v-model="userData.password">
                    </div>
                    <label for="storage">Store in Database?</label>
                    <br>
                    <label for="yes">
                        <input
                                type="radio"
                                id="yes"
                                value="Yes"
                                v-model="storage"> Yes
                    </label>
                    <label for="no">
                        <input
                                type="radio"
                                id="no"
                                value="No"
                                v-model="storage"> No
                    </label>
                </div>

                    <br>
                    <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                        <button
                            class="btn btn-primary"
                            @click.prevent="submited=true">Submit!
                        </button>
                    </div>
            </form>
        </div>

        <div v-else class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userData.firstName }} {{ userData.lastName }} </p>
                        <p>Mail: {{ userData.email }} </p>
                        <p>Password: {{userData.password}} </p>
                        <p>Store in Database? {{ storage }}. </p>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {
  data() {
    return {
      userData: {
        firstName: "",
        lastName: "",
        email: "",
        password: ""
        // baseSwitch: true
      },
      storage: "Yes",
      submited: false
    };
  }
};
</script>

<style>
</style>
