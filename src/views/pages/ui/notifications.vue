<script>
import Layout from "../../layouts/main";
import PageHeader from "@/components/Page-header";
import appConfig from "../../../../app.config";

/**
 * Notifications component
 */
export default {
  page: {
    title: "Notifications",
    meta: [{ name: "description", content: appConfig.description }],
  },
  components: {
    Layout,
    PageHeader,
  },
  data() {
    return {
      title: "Notifications",
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
          text: "Notifications",
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
      <div class="col-xl-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Default Alert</h4>
            <p class="sub-header">
              Alerts are available for any length of text, as well as an
              optional dismiss button. For proper styling, use one of the eight
              <strong>required</strong> contextual classes (e.g.,
              <code>variant</code>).
            </p>

            <b-alert show variant="primary"
              >This is a primary alert—check it out!</b-alert
            >
            <b-alert show variant="secondary"
              >This is a secondary alert—check it out!</b-alert
            >
            <b-alert show variant="success">
              <i class="mdi mdi-check-all me-2"></i>This is a success
              alert—check it out!
            </b-alert>
            <b-alert show variant="danger">
              <i class="mdi mdi-block-helper me-2"></i>This is a danger
              alert—check it out!
            </b-alert>
            <b-alert show variant="warning">
              <i class="mdi mdi-alert-outline me-2"></i>This is a warning
              alert—check it out!
            </b-alert>
            <b-alert show variant="info">
              <i class="mdi mdi-alert-circle-outline me-2"></i>A simple info
              alert with an example link. Give it a click if you like.
            </b-alert>
            <b-alert show variant="light"
              >A simple light alert with an example link. Give it a click if you
              like.</b-alert
            >
            <b-alert show variant="dark" class="mb-0"
              >A simple dark alert with an example link. Give it a click if you
              like.</b-alert
            >
          </div>
          <!-- end card-box-->
        </div>
      </div>
      <!-- end col -->
      <div class="col-xl-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Dismissing Alerts</h4>
            <p class="sub-header">
              Add a dismiss button and the
              <code>.alert-dismissible</code> class, which adds extra padding to
              the right of the alert and positions the
              <code>.close</code> button.
            </p>

            <b-alert show dismissible variant="primary"
              >This is a primary alert—check it out!</b-alert
            >
            <b-alert show dismissible variant="secondary"
              >This is a secondary alert—check it out!</b-alert
            >
            <b-alert show dismissible variant="success"
              >This is a success alert—check it out!</b-alert
            >
            <b-alert show dismissible variant="danger"
              >This is a danger alert—check it out!</b-alert
            >
            <b-alert show dismissible variant="warning"
              >This is a warning alert—check it out!</b-alert
            >
            <b-alert show dismissible
              >This is a info alert—check it out!</b-alert
            >
            <b-alert show dismissible variant="light"
              >This is a light alert—check it out!</b-alert
            >
            <b-alert show dismissible variant="dark" class="mb-0"
              >This is a dark alert—check it out!</b-alert
            >
          </div>
        </div>
        <!-- end card-box-->
      </div>
      <!-- end col -->
    </div>

    <div class="row">
      <div class="col-lg-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Custom Background Alert</h4>
            <p class="sub-header">
              Use
              <code>.bg-*</code>, <code>.border-0</code> classes.
            </p>

            <b-alert show class="bg-white text-primary"
              >This is a primary alert—check it out!</b-alert
            >
            <b-alert show class="bg-white text-secondary"
              >This is a secondary alert—check it out!</b-alert
            >
            <b-alert show class="bg-white text-success"
              >This is a success alert—check it out!</b-alert
            >
            <b-alert show class="bg-white text-danger"
              >This is a danger alert—check it out!</b-alert
            >
            <b-alert show class="bg-white text-warning"
              >This is a warning alert—check it out!</b-alert
            >
            <b-alert show class="bg-white text-info"
              >This is a info alert—check it out!</b-alert
            >
            <b-alert show class="bg-white text-dark mb-0"
              >This is a dark alert—check it out!</b-alert
            >
          </div>
        </div>
        <!-- end card-box-->
      </div>

      <div class="col-lg-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Dismissing Custom Background Alert</h4>
            <p class="sub-header">
              Use
              <code>.bg-*</code>, <code>.border-0</code> classes.
            </p>
            <b-alert show dismissible class="bg-primary text-white border-0"
              >This is a primary alert—check it out!</b-alert
            >
            <b-alert show dismissible class="bg-secondary text-white border-0"
              >This is a secondary alert—check it out!</b-alert
            >
            <b-alert show dismissible class="bg-success text-white border-0"
              >This is a success alert—check it out!</b-alert
            >
            <b-alert show dismissible class="bg-danger text-white border-0"
              >This is a danger alert—check it out!</b-alert
            >
            <b-alert show dismissible class="bg-warning text-white border-0"
              >This is a warning alert—check it out!</b-alert
            >
            <b-alert show dismissible class="bg-info text-white border-0"
              >This is a light alert—check it out!</b-alert
            >
            <b-alert show dismissible class="bg-dark text-white border-0 mb-0"
              >This is a dark alert—check it out!</b-alert
            >
          </div>
        </div>
      </div>
    </div>
  </Layout>
</template>
