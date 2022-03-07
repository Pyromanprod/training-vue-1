<template>
  <div class="pass-input">
    <label for="pass">Mot de passe</label>
    <input type="password" id="pass" v-model="password">
    <ul>
      <li :class="{validate : checkNbChar()}">8 Caractère</li>
      <li :class="{validate : checkUpper()}">1 Majuscule</li>
      <li :class="{validate : checkLower()}">1 Minuscule</li>
      <li :class="{validate : checkSpecialChar()}">1 Caractère spécial</li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'PassInput',
  data() {
    return {
      password: '',
    }
  },
  methods:{
    checkNbChar(){
      return this.password.length>=8;
    },
    checkUpper(){
      return /[A-Z]/.test(this.password);
    },
    checkLower(){
      return /[a-z]/.test(this.password);
    },
    checkSpecialChar(){
      return /[!"#$%&'()*+,-./:;<=>?@[\\\]^_`{|}~]/.test(this.password);
    }
  }

}
</script>

<style scoped>
li{
  list-style: none;
}
.validate{
  color: green;
  font-weight: bold;
}
.validate:before{
  content: '✔ ';
}
</style>