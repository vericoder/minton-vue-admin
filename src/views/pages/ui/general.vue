<script>
import Layout from "../../layouts/main";
import PageHeader from "@/components/Page-header";
import appConfig from "../../../../app.config";

/**
 * General UI component
 */
export default {
  page: {
    title: "General UI",
    meta: [{ name: "description", content: appConfig.description }],
  },
  components: {
    Layout,
    PageHeader,
  },
  data() {
    return {
      title: "General UI",
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
          text: "General UI",
          active: true,
        },
      ],
      currentpage: 3,
      page: 1
    };
  },
};
</script>

<template>
  <Layout>
    <PageHeader :title="title" :items="items" />
    <div class="row">
      <div class="col-xl-12">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Default</h4>
            <p class="sub-header">
              A simple labeling component. Badges scale to match the size of the
              immediate parent element by using relative font sizing and
              <code>em</code> units.
            </p>

            <h1>
              h1.Example heading
              <b-badge class="bg-secondary">New</b-badge>
            </h1>
            <h2>
              h2.Example heading
              <b-badge class="badge-soft-success">New</b-badge>
            </h2>
            <h3>
              h3.Example heading
              <button type="button" class="btn btn-sm btn-primary">
                Notifications
                <b-badge class="bg-light text-dark">4</b-badge>
              </button>
            </h3>
            <h4>
              h4.Example heading
              <b-badge href="#" variant="dark" class="badge-soft-info"
                >Info Soft</b-badge
              >
            </h4>
            <h5>
              h5.Example heading
              <b-badge class="badge-outline-warning">New</b-badge>
            </h5>
            <h6>h6.Example heading <b-badge class="bg-danger">New</b-badge></h6>
          </div>
          <!-- end card-body -->
        </div>
        <!-- end card-->
      </div>
      <!-- end col-->
    </div>
    <div class="row">
      <div class="col-xl-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Contextual variations</h4>
            <p class="sub-header">
              Add any of the below mentioned modifier classes to change the
              appearance of a badge. Badge can be more contextual as well. Just
              use regular convention e.g. <code>badge-*color</code>,
              <code>badge-primary</code>
              to have badge with different background.
            </p>

            <b-badge class="bg-primary me-1">Primary</b-badge>
            <b-badge class="bg-secondary me-1" variant="secondary"
              >Secondary</b-badge
            >
            <b-badge class="bg-success me-1" variant="success">Success</b-badge>
            <b-badge class="bg-danger me-1" variant="danger">Danger</b-badge>
            <b-badge class="bg-warning me-1" variant="warning">Warning</b-badge>
            <b-badge class="bg-info me-1" variant="info">Info</b-badge>
            <b-badge class="bg-pink me-1" variant="pink">Pink</b-badge>
            <b-badge class="bg-purple me-1" variant="purple">Purple</b-badge>
            <b-badge class="bg-light text-dark me-1" variant="light">Light</b-badge>
            <b-badge class="bg-dark" variant="dark">Dark</b-badge>

            <h5 class="mt-4">Soft Badges</h5>
            <p class="sub-header">
              Using the <code>.badge-soft*</code> modifier class, you can have
              more soften variation.
            </p>

            <b-badge class="badge-soft-primary me-1">Primary</b-badge>
            <b-badge class="badge-soft-secondary me-1">Secondary</b-badge>
            <b-badge class="badge-soft-success me-1">Success</b-badge>
            <b-badge class="badge-soft-danger me-1">Danger</b-badge>
            <b-badge class="badge-soft-warning me-1">Warning</b-badge>
            <b-badge class="badge-soft-info me-1">Info</b-badge>
            <b-badge class="badge-soft-pink me-1">Pink</b-badge>
            <b-badge class="badge-soft-purple me-1">Purple</b-badge>
            <b-badge class="badge-soft-light me-1">Light</b-badge>
            <b-badge class="badge-soft-dark">Dark</b-badge>

            <h5 class="mt-4">Outline Badges</h5>
            <p class="sub-header">
              Using the <code>.badge-outline-*</code> to quickly create a
              bordered badges.
            </p>

            <b-badge class="badge-outline-primary me-1">Primary</b-badge>
            <b-badge class="badge-outline-secondary me-1">Secondary</b-badge>
            <b-badge class="badge-outline-success me-1">Success</b-badge>
            <b-badge class="badge-outline-danger me-1">Danger</b-badge>
            <b-badge class="badge-outline-warning me-1">Warning</b-badge>
            <b-badge class="badge-outline-info me-1">Info</b-badge>
            <b-badge class="badge-outline-pink me-1">Pink</b-badge>
            <b-badge class="badge-outline-purple me-1">Purple</b-badge>
            <b-badge class="badge-outline-light me-1">Light</b-badge>
            <b-badge class="badge-outline-dark">Dark</b-badge>
          </div>
          <!-- end card-body -->
        </div>
        <!-- end card-->
      </div>
      <!-- end col -->

      <div class="col-xl-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Pill Badges</h4>
            <p class="sub-header">
              Use the <code>pill</code> modifier class to make badges more
              rounded.
            </p>

            <b-badge class="bg-primary rounded-pill me-1" variant="primary"
              >Primary</b-badge
            >
            <b-badge class="bg-secondary rounded-pill me-1" variant="secondary"
              >Secondary</b-badge
            >
            <b-badge class="bg-success rounded-pill me-1" variant="success"
              >Success</b-badge
            >
            <b-badge class="bg-danger rounded-pill me-1" variant="danger"
              >Danger</b-badge
            >
            <b-badge class="bg-warning rounded-pill me-1" variant="warning"
              >Warning</b-badge
            >
            <b-badge class="bg-info rounded-pill me-1" variant="info">Info</b-badge>
            <b-badge class="bg-pink rounded-pill me-1" variant="pink">Pink</b-badge>
            <b-badge class="bg-purple rounded-pill me-1" variant="purple"
              >Purple</b-badge
            >
            <b-badge class="bg-light rounded-pill text-dark me-1" variant="light"
              >Light</b-badge
            >
            <b-badge class="bg-dark rounded-pill" variant="dark">Dark</b-badge>

            <h5 class="mt-4">Soft Badges</h5>
            <p class="sub-header">
              Use the <code>.badge-soft-*</code> modifier class to make badges
              soft.
            </p>

            <b-badge class="badge-soft-primary rounded-pill me-1" pill
              >Primary</b-badge
            >
            <b-badge class="badge-soft-secondary rounded-pill me-1" pill
              >Secondary</b-badge
            >
            <b-badge class="badge-soft-success rounded-pill me-1" pill
              >Success</b-badge
            >
            <b-badge class="badge-soft-danger rounded-pill me-1" pill
              >Danger</b-badge
            >
            <b-badge class="badge-soft-warning rounded-pill me-1" pill
              >Warning</b-badge
            >
            <b-badge class="badge-soft-info rounded-pill me-1" pill>Info</b-badge>
            <b-badge class="badge-soft-pink rounded-pill me-1" pill>Pink</b-badge>
            <b-badge class="badge-soft-purple rounded-pill me-1" pill
              >Purple</b-badge
            >
            <b-badge class="badge-soft-light rounded-pill me-1" pill>Light</b-badge>
            <b-badge class="badge-soft-dark rounded-pill" pill>Dark</b-badge>

            <h5 class="mt-4">Outline Badges</h5>
            <p class="sub-header">
              Using the <code>.badge-outline-*</code> to quickly create a
              bordered badges.
            </p>

            <b-badge class="badge-outline-primary rounded-pill me-1" pill
              >Primary</b-badge
            >
            <b-badge class="badge-outline-secondary rounded-pill me-1" pill
              >Secondary</b-badge
            >
            <b-badge class="badge-outline-success rounded-pill me-1" pill
              >Success</b-badge
            >
            <b-badge class="badge-outline-danger rounded-pill me-1" pill
              >Danger</b-badge
            >
            <b-badge class="badge-outline-warning rounded-pill me-1" pill
              >Warning</b-badge
            >
            <b-badge class="badge-outline-info rounded-pill me-1" pill>Info</b-badge>
            <b-badge class="badge-outline-pink rounded-pill me-1" pill>Pink</b-badge>
            <b-badge class="badge-outline-purple rounded-pill me-1" pill
              >Purple</b-badge
            >
            <b-badge class="badge-outline-light rounded-pill me-1" pill
              >Light</b-badge
            >
            <b-badge class="badge-outline-dark rounded-pill" pill>Dark</b-badge>
          </div>
          <!-- end card-body -->
        </div>
        <!-- end card -->
      </div>
    </div>

    <div class="row">
      <div class="col-12">
        <div class="card">
          <div class="card-body">
            <div class="row">
              <div class="col-md-6">
                <div class="">
                  <h4 class="header-title">Pagination</h4>
                  <p class="text-muted font-14 mb-3">
                    Provide pagination links for your site or app with the
                    multi-page pagination component.
                  </p>

                  <p class="mb-1 fw-bold">Default Pagination</p>
                  <p class="text-muted font-14">
                    Simple pagination inspired by Rdio, great for apps and
                    search results.
                  </p>

                  <b-pagination
                    v-model="page"
                    :total-rows="50"
                    :per-page="10"
                    aria-controls="my-table"
                  ></b-pagination>

                  <p class="mb-1 fw-bold mt-4">Rounded Pagination</p>
                  <p class="text-muted font-14">
                    Add
                    <code>.pagination-rounded</code> for rounded pagination.
                  </p>
                  <b-pagination
                    v-model="currentpage"
                    class="pagination-rounded"
                    :total-rows="50"
                    :per-page="10"
                    aria-controls="my-table"
                  ></b-pagination>

                  <p class="mb-1 fw-bold mt-4">Sizing</p>
                  <p class="text-muted font-14">
                    Add
                    <code>.pagination-lg</code>
                    or
                    <code>.pagination-sm</code>
                    for additional sizes.
                  </p>

                  <b-pagination
                    size="lg"
                    :total-rows="30"
                    :per-page="10"
                    aria-controls="my-table"
                  ></b-pagination>

                  <b-pagination
                    size="sm"
                    :total-rows="30"
                    :per-page="10"
                    aria-controls="my-table"
                  ></b-pagination>

                  <p class="mb-1 fw-bold mt-4">Alignment</p>
                  <p class="text-muted font-14">
                    Change the alignment of pagination components with flexbox
                    utilities.
                  </p>

                  <b-pagination
                    :total-rows="30"
                    first-text="First"
                    prev-text="Previous"
                    next-text="Next"
                    last-text="Last"
                    align="center"
                  ></b-pagination>

                  <b-pagination
                    :total-rows="30"
                    first-text="First"
                    prev-text="Previous"
                    next-text="Next"
                    last-text="Last"
                    align="right"
                  ></b-pagination>
                </div>
              </div>
              <div class="col-md-6">
                <div class="">
                  <h4 class="header-title mt-3 mt-sm-0">Breadcrumb</h4>
                  <p class="text-muted font-14">
                    Indicate the current page’s location within a navigational
                    hierarchy.
                  </p>

                  <ol class="breadcrumb">
                    <li class="breadcrumb-item active">Home</li>
                  </ol>
                  <ol class="breadcrumb">
                    <li class="breadcrumb-item">
                      <a>Home</a>
                    </li>
                    <li class="breadcrumb-item active">Library</li>
                  </ol>
                  <ol class="breadcrumb">
                    <li class="breadcrumb-item">
                      <a>Home</a>
                    </li>
                    <li class="breadcrumb-item">
                      <a>Library</a>
                    </li>
                    <li class="breadcrumb-item active">Data</li>
                  </ol>
                </div>
              </div>
            </div>
            <!-- end card-body-->
          </div>
          <!-- end card -->
        </div>
        <!-- end col -->
      </div>
    </div>
    <!-- end row -->
  </Layout>
</template>
