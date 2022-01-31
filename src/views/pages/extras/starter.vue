<script>
import Layout from "../../layouts/main";
import PageHeader from "@/components/Page-header";

/**
 * Starter component
 */
export default {
  data() {
    return {
      title: "Starter",
      items: [
        {
          text: "Minton",
          href: "/",
        },
        {
          text: "Pages",
          href: "/",
        },
        {
          text: "Starter",
          active: true,
        },
      ],
    };
  },
  components: {
    Layout,
    PageHeader,
  },
};
</script>

<template>
  <Layout>
    <PageHeader :title="title" :items="items" />
  </Layout>
</template>
