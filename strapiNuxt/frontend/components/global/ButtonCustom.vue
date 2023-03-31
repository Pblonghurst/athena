<template>
    <button @click="handleClick">{{ this.text }}</button>
</template>

<script>
export default {
    name: 'ButtonCustom',
    props: {
        text: String,
        index: Number
    },
    methods: {
    handleClick() {
      this.$emit('button-click', this.index);
    },
  },
}
</script>

