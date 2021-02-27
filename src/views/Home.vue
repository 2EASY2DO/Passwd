<template>
  <div class="home"> 
    <h1 class="text-red-400">Put Left Side</h1>
    <div>
      <div> 
        <input v-model="caps" type="checkbox" id="caps" name="caps" value="caps">
        <label for="caps"> Use Caps</label>
      </div>
      <div>
        <input v-model="nums" type="checkbox" id="numbers" name="numbers" value="numbers">
        <label for="numbers"> Use Number</label>
      </div>
      <div>
        <input v-model="sym" type="checkbox" id="symbols" name="symbols" value="symbols">
        <label for="symbols"> Use Symbols</label> 
      </div>
    </div> 
    <h1>choose to ahve a text box for user to inoput length instead of the slider</h1>
    <input v-model="length" type="text" id="length" name="length"> 
    <h1 class="text-red-400">Put Right Side</h1>
    <h1>{{password}}</h1>
    <button v-on:click="createpasswd" class="bg-red-400 rounded-md w-16 h-10 hover:bg-green-400 focus:bg-green-400 focus:ring-2 focus:outline-none focus:ring-red-400">Copy</button> 
    <h1>button to save password to file in pc, it will also copy the password to clipboard</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    
  },
  data() {
    return {
      password: "Click the button to make a new password",
      length: 8,
      caps: false,
      nums: false,
      sym: false
    }
  },
  methods: {
  createpasswd() {
    this.password = "";
    let letters = "abcdefghijklmnopqrstuvwxyz";

    if (this.caps == true){letters += "ABCDEFGHIJKLMNOPQRSTUVWXYZ"}
    if (this.nums == true){letters += "123456789"}
    if (this.sym == true){letters += "!@#$%&_+"}

    for(let i = 1; i <=this.length; i++){
      let char = Math.round(Math.random()
                            * letters.length + 1);
     // Testing a new way of working with teh checkboxes
     //if (this.caps == true){
      //  if (Math.round(Math.random()) > 0){ 
      //   this.password += letters.charAt(char).toUpperCase();
      //  } else {
      //    this.password += letters.charAt(char);
      //  }
      //}
      this.password += letters.charAt(char)
    } 
    }
  }
}

</script>
