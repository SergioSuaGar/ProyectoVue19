<template>
    <div class="about">
        <Header></Header>
        <Section></Section>
        <Footer></Footer>
    </div>
</template>

<script>

    import Header from "../components/Header";
    import Section from "../components/Section";
    import Footer from "../components/Footer";

    export default {
        name: "meteo",
        components: {
            Header,
            Section,
            Footer
        }
    }
</script>

<style scoped>

</style>