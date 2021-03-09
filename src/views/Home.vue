<template>
  <div class="home"> 
    <h1 class="text-red-400">Put Left Side</h1>
    <div>
      <h1 class="text-blue-500 font-black">Options</h1>
      <div> 
        <input v-model="caps" type="checkbox" id="caps" name="caps" value="caps">
        <label for="caps" class="text-white"> Use Caps</label>
      </div>
      <div>
        <input v-model="nums" type="checkbox" id="numbers" name="numbers" value="numbers">
        <label for="numbers" class="text-white"> Use Number</label>
      </div>
      <div>
        <input v-model="sym" type="checkbox" id="symbols" name="symbols" value="symbols">
        <label for="symbols" class="text-white"> Use Symbols</label> 
      </div>
    <input v-model="length" type="text" id="length" name="length">  
    </div>  
    <h1 class="text-red-400">Put Right Side</h1>
    <div>
      <h1 class="text-blue-500 font-black">Result</h1>
      <h1 class="text-green-400">{{password}}</h1>
      <div class="flex space-x-4 items-centerv justify-center">
        <button v-on:click="createpasswd" class="text-black bg-red-400 rounded-md w-20 h-12 hover:bg-green-400 hover:text-white focus:bg-green-400 focus:ring-2 focus:outline-none focus:ring-red-400">Create Password</button> 
        <button v-on:click="copy" class="text-black bg-red-400 rounded-md w-12 h-10 hover:bg-green-400 hover:text-white focus:bg-green-400 focus:ring-2 focus:outline-none focus:ring-red-400">Copy</button>  
      </div>
    </div>
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
      length: 12,
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
      this.password += letters.charAt(char)
    } 
    },
  copy() {
    navigator.clipboard.writeText(this.password)  
  }
  }
}

</script>
