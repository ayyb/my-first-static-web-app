<template>
  <div>Hello {{ value }}

    <span>메세지 {{ message }}</span>
    <button @click="handleClick">클릭</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      value: "World"
    };
  },
  async mounted() {
    const { text } = await (await fetch("/api/message")).json();
    this.value = text;
  },
  handleClick(){
    alert("클릭됨")
  }
};
</script>
