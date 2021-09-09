<template>
  <main>
    <div>{{ VueShowClient.currentClient.address }}</div>
  </main>
</template>

<script>
export default {
  data: () => ({
    VueShowClient: {},
  }),
  mounted() {
    this.VueShowClient = this.coachViewContext.binding.value;
    console.log(this.VueShowClient);
    //console.log(this.kierunkiStudiow);
  },
  methods: {
    showPerson(e) {
      this.pickedClient = [];
      const pickedElement = e.target.parentNode.id;
      const person = this.clientList[pickedElement];
      this.pickedClient.push(person);
      this.personDataIsVisible = true;
    },
    showTestResult() {
      console.log(this.pickedClient);
    },
    closeClientData() {
      this.personDataIsVisible = false;
      this.pickedClient = [];
    },
    searchClient() {
      this.coachViewContext.binding.set("value",this.VueShowClient);
      
      // const clientPesel = document.querySelectorAll(".oneClient tr .pesel");
      // console.log(
      //   clientPesel.forEach((pesel) => {
      //     const client = pesel.parentNode.parentNode;
      //     if (this.typedPesel !== pesel.textContent) {
      //       client.style.display = "none";
      //     } else {
      //       client.style.display = "flex";
      //     }
      //     console.log(pesel.textContent);
      //     console.log(pesel.parentNode.parentNode);
      //   })
      // );
      console.log(this.clientList);
    },
  },
};
</script>

<style scoped>
@import "./css/app.css";
</style>
