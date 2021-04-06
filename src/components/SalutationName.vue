<template>
  <div>
    <select @change="$emit('update:salutation', $event.target.value)">
      <option value=""></option>
      <option
        v-for="(item, index) in salutations"
        :key="index"
        :value="item"
        :selected="salutation === item"
      >
        {{ item }}
      </option>
    </select>

    <input
    @input="$emit('update:name', $event.target.value)"
      :input="name"
      type="text"
    />
  </div>
</template>

<script>
const salutations = ['Ms.', 'Mrs.', 'Miss', 'Mx.', 'Dr.']

export default {
  props: {
    salutation: {
      type: String,
      default: ''
    },
    name: {
      type: String,
      default: ''
    }
  },
  setup () {
    return {
      salutations
    }
  }
}
</script>

<style lang="scss" scoped>
div {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}

select {
  margin-right: 0.5rem;
}

input {
  width: 50%;
}
</style>
