<template>
  <form>
    <label for="name">NAME</label>
    <input
      id="name" name="name" type="text"
      v-model="name" @input="$emit('name-change', $event.target.value)" />

    <div>
      <h5>Address</h5>
      <label for="address1">Address line 1</label>
      <input
        id="address1" name="address1" type="text"
        v-model="address1" @input="$emit('address1-change', $event.target.value)" />

      <label for="address2">Address line 2</label>
      <input
        id="address2" name="address2" type="text"
        v-model="address2" @input="$emit('address2-change', $event.target.value)" />

      <label for="address3">Address line 3</label>
      <input
        id="address3" name="address3" type="text"
        v-model="address3" @input="$emit('address3-change', $event.target.value)" />
    </div>

  </form>
</template>

<script>
export default {
  name: 'Form',
  data() {
    return {
      name: "",
      address1: "",
      address2: "",
      address3: "",
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
}
</style>
