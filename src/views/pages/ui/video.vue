<script>
import Layout from "../../layouts/main";
import PageHeader from "@/components/Page-header";
import appConfig from "../../../../app.config";

/**
 * Embed Video component
 */
export default {
  page: {
    title: "Embed Video",
    meta: [{ name: "description", content: appConfig.description }],
  },
  components: {
    Layout,
    PageHeader,
  },
  data() {
    return {
      title: "Embed Video",
      items: [
        {
          text: "Minton",
          href: "/",
        },
        {
          text: "UI",
          href: "/",
        },
        {
          text: "Embed Video",
          active: true,
        },
      ],
    };
  },
};
</script>

<template>
  <Layout>
    <PageHeader :title="title" :items="items" />

    <div class="row">
      <div class="col-lg-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Ratios video 21:9</h4>
            <p class="sub-header">Use class <code>.ratio-21x9</code></p>

            <!-- 21:9 aspect ratio -->
            <div class="ratio ratio-21x9">
              <iframe
                src="https://www.youtube.com/embed/PrUxWZiQfy4?autohide=0&amp;showinfo=0&amp;controls=0"
              ></iframe>
            </div>
          </div>
        </div>
      </div>
      <!-- end col -->

      <div class="col-lg-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Ratios video 16:9</h4>
            <p class="sub-header">Use class <code>.ratio-16x9</code></p>

            <!-- 16:9 aspect ratio -->
            <div class="ratio ratio-16x9">
              <iframe
                src="https://www.youtube.com/embed/PrUxWZiQfy4?ecver=1"
              ></iframe>
            </div>
          </div>
        </div>
      </div>
      <!-- end col -->
    </div>
    <!-- end row -->

    <div class="row">
      <div class="col-lg-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Ratios video 4:3</h4>
            <p class="sub-header font-13">
              Use class <code>.ratio-4x3</code>
            </p>

            <!-- 4:3 aspect ratio -->
            <div class="ratio ratio-4x3">
              <iframe
                src="https://www.youtube.com/embed/PrUxWZiQfy4?ecver=1"
              ></iframe>
            </div>
          </div>
        </div>
      </div>
      <!-- end col -->

      <div class="col-lg-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Ratios video 1:1</h4>
            <p class="sub-header">Use class <code>.ratio-1x1</code></p>

            <!-- 1:1 aspect ratio -->
            <div class="ratio ratio-1x1">
              <iframe
                src="https://www.youtube.com/embed/PrUxWZiQfy4?ecver=1"
              ></iframe>
            </div>
          </div>
        </div>
      </div>
      <!-- end col -->
    </div>
    <!-- end row -->
  </Layout>
</template>
