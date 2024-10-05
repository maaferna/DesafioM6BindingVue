<template>
  <div id="app">
    <form @submit.prevent>
      <div>
        <label>Título de la tarjeta:</label>
        <input 
        v-model="cardTitle"
        @input="updateCardTitle"
         />
      </div>
      <div>
        <label>Chip SRC:</label>
        <input 
          v-model="chipInput" 
          @input="updateChipSrc" 
          placeholder="Enter /chip.png" />
      </div>
      <div>
        <label>Número:</label>
        <input 
          v-model="cardNumber"
          @input="formatCardNumber" 
          placeholder="400500600700"
          maxlength="15"
          />
      </div>
      <div>
        <label>Fecha de expiración:</label>
        <input v-model="expirationDate" />
      </div>
      <div>
        <label>Propietario:</label>
        <input v-model="owner" />
      </div>
      <div>
        <label>Tipo de tarjeta SRC:</label>
        <input 
          v-model="cardTypeInput" 
          @input="updateCardTypeSrc" 
          placeholder="Enter /visa.png" />
      </div>
    </form>

    <div class="carnet">
      <h3>{{ cardTitle }}</h3>
      <img :src="chipSrc" alt="Chip" width="40" />
      <div>
        <h2>{{ cardNumber }}</h2>
        <span class="expiration">Fecha Exp: <b>{{ expirationDate }}</b></span>
      </div>
      <footer>
        <span>{{ owner }}</span>
        <img :src="cardTypeSrc" width="60" />
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cardTitle: '',
      chipInput: '/chip.png',  
      cardTypeInput: '/visa.png',  
      cardNumber: '',
      expirationDate: '',
      owner: '',
    };
  },
  computed: {
    chipSrc() {
      return `/assets${this.chipInput}`; 
    },
    cardTypeSrc() {
      return `/assets${this.cardTypeInput}`; 
    },
    formattedCardTitle() {
      return this.cardTitle.toUpperCase(); 
    },
  },
  methods: {
    updateChipSrc() {
      this.chipInput = this.chipInput.trim(); 
    },
    updateCardTypeSrc() {
      this.cardTypeInput = this.cardTypeInput.trim(); 
    },
    updateCardTitle() {
      this.cardTitle = this.cardTitle.toUpperCase(); 
    },
    formatCardNumber() {
      const numbers = this.cardNumber.replace(/\D/g, '');
      const formatted = numbers.match(/.{1,3}/g)?.join(' ') || '';
      this.cardNumber = formatted; 
    },
  },
};
</script>

<style>
* {
  margin: 0;
}
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  font-size: 14px;
  font-family: sans-serif;
}

#app {
  display: flex;
  gap: 40px;
}
form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}
form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

form div label {
  text-align: right;
}

.carnet {
  width: 400px;
  height: 230px;
  background: #1c1a1e;
  color: white;
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px 2px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

h3 {
  font-size: 20px;
  text-align: left
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
  text-align: left;
}

b {
  font-size: 16px;
}

.expiration { 
  display: block; 
  text-align: left; 
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>
