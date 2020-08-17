<template>
  <div role="alert" :title="text" v-if="text">
    <svg version="1.0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 50 50">
      <path
        d="M26.5 44.9c-1-1-1.5-2.2-1.5-3.6 0-.9.3-1.7.8-2.5s1.2-1.4 2-1.8c.8-.5 1.7-.7 2.6-.7.9 0 1.8.2 2.6.7.8.5 1.5 1.1 2 1.8.5.8.8 1.6.8 2.5 0 1.4-.5 2.6-1.5 3.6s-2.3 1.5-3.9 1.5-2.9-.5-3.9-1.5zm.5-10.7c-.2-.2-.3-.4-.3-.7l-.8-20v-.1c0-.5.3-.8.9-.8h7.3c.3 0 .5.1.7.2.2.2.2.4.2.7l-.9 20c0 .6-.4.9-1 .9h-5.4c-.3 0-.5-.1-.7-.2z"
        fill="#e6312c"
      />
    </svg>
  </div>
</template>

<script>
export default {
    props: {
        text: {
            type: String
        }
    }
}
</script>

<style scoped>
div {
    position: absolute;
    bottom: 12px;
    right: 0px;
    width: 20px;
    height: 20px;
    cursor: help;
}
</style>