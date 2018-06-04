<template>


  
</template>

<script>
export default {
  data: () => {
    return {
      valid: false,
      moneda: null,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => v.length <= 10 || 'Name must be less than 10 characters'
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
      ],
      items: [
        {'iso': 'USD', 'name': 'dolar'},
        {'iso': 'VEF', 'name': 'bolivar'}
      ]
    }
  }
}
</script>

<style>

</style>
