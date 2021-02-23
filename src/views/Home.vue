<template>
  <div class="home"> 
    <h1 class="text-red-400">Put Left Side</h1>
    <div>
      <div> 
        <input class="form-checkbox h-5 w-5 bg-orange-600" type="checkbox" id="caps" name="caps" value="caps">
        <label for="caps"> Use Caps</label>
      </div>
      <div>
        <input type="checkbox" id="numbers" name="numbers" value="numbers">
        <label for="numbers"> Use Number</label>
      </div>
      <div>
        <input type="checkbox" id="symbols" name="symbols" value="symbols">
        <label for="symbols"> Use Symbols</label> 
      </div>
    </div> 
    <h1>choose to ahve a text box for user to inoput length instead of the slider</h1>
    <input type="text" id="length" name="length"> 
    <h1 class="text-red-400">Put Right Side</h1>
    <h1>password generated goes here</h1>
    <button class="bg-red-400 rounded-md w-16 h-10 hover:bg-green-400 focus:bg-green-400 focus:ring-2 focus:outline-none focus:ring-red-400">Copy</button> 
    <h1>button to save password to file in pc, it will also copy the password to clipboard</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    
  }
}
</script>
