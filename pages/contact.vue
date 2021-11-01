<template>
  <div>

    <PageHeader title="Магазины" />
    <ContactPage />

  </div>
</template>
<script>
 
  import PageHeader from "../components/PageHeader"
  import ContactPage from "../components/ContactPage";
  export default {
    components: {
      ContactPage,
      PageHeader,
     
    },
    head(){
      return {
        title: "Контакты"
      }
    }
  }
</script>
