<script>
export default {
  data() {
    return {
      generatedPassword: '' // Inizializza generatedPassword come una stringa vuota
    };
  },

  methods: {
    generatePassword() {
      this.generatedPassword = this.generateString(15); // Assegna la password generata a generatedPassword
    },

    generateString(length) {
      const characters = 'AbCdEfGhIjKlMnOpQrStUvWxYz0123456789@!.?$';
      let result = '';
      const charactersLength = characters.length;
      for (let i = 0; i < length; i++) {
        result += characters.charAt(Math.floor(Math.random() * charactersLength));
      }
      return result;
    }
  }
};
</script>

<template>
  <div class="container">
    <button class="generate-password" @click="generatePassword">Genera Password</button>
    <h1>{{ generatedPassword }}</h1>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

h1 {
  background-color: #4793AF;
  padding: 12px;
  color: white;
  border-radius: 4px;
}
.container {
  max-width: 1024px;
  margin: 0 auto;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 30px;
}

.generate-password {
  background-color: coral;
  color: white;
  padding: 7px 9px;
  border: none;
  border-radius: 4px;
}
</style>
