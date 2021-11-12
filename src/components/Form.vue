<template>
  <form>
    <label for="name" class="form-label">{{ type === 'groom' ? 'GROOM NAME' : 'BRIDE NAME' }}</label>
    <input
      class="form-control" :placeholder="type === 'groom' ? 'GROOM NAME' : 'BRIDE NAME'"
      :id="type === 'groom' ? 'groom-name' : 'bride-name'" name="name" type="text"
      v-model="name" @input="$emit('name-change', $event.target.value)" />

    <label for="address1">PARENTS' DETAILS</label>
    <input
      class="form-control" placeholder="PARENTS' DETAILS"
      :id="type === 'groom' ? 'groom-address1' : 'bride-address1'" name="address1" type="text"
      v-model="address1" @input="$emit('address1-change', $event.target.value)" />

    <label for="address2">ADDRESS LINE 1</label>
    <input
      class="form-control" placeholder="HOUSE NAME, PLACE, PANCHAYATH"
      :id="type === 'groom' ? 'groom-address2' : 'bride-address2'" name="address2" type="text"
      v-model="address2" @input="$emit('address2-change', $event.target.value)" />

    <labeL FOR="ADDRESS3">ADDRESS LINE 2</label>
    <input
      class="form-control" placeholder="TALUK, DISTRICT, PINCODE"
      :id="type === 'groom' ? 'groom-address3' : 'bride-address3'" name="address3" type="text"
      v-model="address3" @input="$emit('address3-change', $event.target.value)" />
  </form>
</template>

<script>
export default {
  name: 'Form',
  props: {
    type: String
  },
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
  flex-direction: column;
  align-items: center;
}
</style>
