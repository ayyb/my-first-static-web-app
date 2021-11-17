<template>
  <div id="app">
    {{message}}
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: "World"
    };
  },
  async mounted() {
    const { text } = await (await fetch("/api/message")).json();
    console.log(text)
    this.message = text;
  },
  methods: {
    handleClick() {
      alert("클릭됨");
    }
  }
};
</script>
