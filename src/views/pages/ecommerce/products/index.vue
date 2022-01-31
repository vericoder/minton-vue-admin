<script>
import { productData } from "./data";
import Layout from "../../../layouts/main";
import PageHeader from "@/components/Page-header";
import appConfig from "../../../../../app.config";

/**
 * Products-list component
 */
export default {
  components: {
    Layout,
    PageHeader,
  },
  page: {
    title: "Products-list",
    meta: [{ name: "description", content: appConfig.description }],
  },
  data() {
    return {
      productData: productData,
      title: "Products List",
      items: [
        {
          text: "Minton",
        },
        {
          text: "eCommerce",
        },
        {
          text: "Products List",
          active: true,
        },
      ],
      totalRows: 1,
      currentPage: 1,
      perPage: 10,
      pageOptions: [10, 25, 50, 100],
      filter: null,
      filterOn: [],
      sortBy: "age",
      sortDesc: false,
      fields: [
        {
          key: "check",
          label: "",
        },
        {
          key: "name",
          label: "Product",
          sortable: true,
        },
        {
          key: "rating",
          sortable: true,
        },
        {
          key: "category",
          sortable: true,
        },
        {
          key: "date",
          label: "Added Date",
          sortable: true,
        },
        {
          key: "price",
          sortable: true,
        },
        {
          key: "quality",
          sortable: true,
        },
        {
          key: "status",
          label: "Status",
          sortable: true,
        },
        "action",
      ],
    };
  },
  computed: {
    /**
     * Total no. of records
     */
    rows() {
      return this.productData.length;
    },
  },
  mounted() {
    // Set the initial number of items
    this.totalRows = this.items.length;
  },
  methods: {
    /**
     * Search the table data with search input
     */
    onFiltered(filteredItems) {
      // Trigger pagination to update the number of buttons/pages due to filtering
      this.totalRows = filteredItems.length;
      this.currentPage = 1;
    },
  },
};
</script>

<template>
  <Layout>
    <PageHeader :title="title" :items="items" />
    <div class="row">
      <div class="col-12">
        <div class="card">
          <div class="card-body">
            <div class="row mb-2">
              <div class="col-sm-6">
                <router-link
                  to="/ecommerce/product-create"
                  class="btn btn-danger mb-2"
                  ><i class="mdi mdi-plus-circle me-1"></i> Add
                  Products</router-link
                >
              </div>
              <div class="col-sm-6">
                <div class="float-sm-end">
                  <button type="button" class="btn btn-success mb-2 mb-sm-0">
                    <i class="mdi mdi-cog"></i>
                  </button>
                </div>
              </div>
              <!-- end col-->
            </div>
            <div class="row mb-2">
              <div class="col-sm-12 col-md-6">
                <div id="tickets-table_length" class="dataTables_length">
                  <label class="d-inline-flex align-items-center fw-normal">
                    Display&nbsp;
                    <b-form-select
                      v-model="perPage"
                      size="sm"
                      :options="pageOptions"
                      class="form-select form-select-sm mx-1"
                    ></b-form-select
                    >&nbsp;customers
                  </label>
                </div>
              </div>
              <!-- Search -->
              <div class="col-sm-12 col-md-6">
                <div
                  id="tickets-table_filter"
                  class="dataTables_filter text-md-end"
                >
                  <label class="d-inline-flex align-items-center fw-normal">
                    Search:
                    <b-form-input
                      v-model="filter"
                      type="search"
                      class="form-control form-control-sm ms-2"
                    ></b-form-input>
                  </label>
                </div>
              </div>
              <!-- End search -->
            </div>
            <!-- Table -->
            <div class="table-responsive mb-0 datatables">
              <b-table
                table-class="table table-centered w-100"
                thead-tr-class="table-light"
                :items="productData"
                :fields="fields"
                responsive="sm"
                :per-page="perPage"
                :current-page="currentPage"
                :sort-by.sync="sortBy"
                :sort-desc.sync="sortDesc"
                :filter="filter"
                :filter-included-fields="filterOn"
                @filtered="onFiltered"
              >
                <template v-slot:cell(check)="data">
                  <div class="form-check font-16 mb-0">
                    <input
                      class="form-check-input dt-checkboxes"
                      type="checkbox"
                      :id="`contacusercheck${data.item.id}`"
                    />
                    <label
                      class="form-check-label"
                      :for="`contacusercheck${data.item.id}`"
                      >&nbsp;</label
                    >
                  </div>
                </template>

                <template v-slot:cell(name)="data">
                  <img
                    v-if="data.item.image"
                    :src="data.item.image"
                    alt=""
                    class="rounded me-3"
                    height="48"
                  />
                  <div
                    v-if="!data.item.image"
                    class="avatar-xs d-inline-block me-2"
                  >
                    <div
                      class="avatar-title bg-soft-primary rounded-circle text-primary"
                    >
                      <i class="mdi mdi-account-circle m-0"></i>
                    </div>
                  </div>
                  <h5 class="m-0 d-inline-block align-middle">
                    <a href="#" class="text-dark">{{ data.item.name }}</a>
                  </h5>
                </template>
                <template v-slot:cell(price)="data">
                  $ {{ data.item.price }}
                </template>
                <template v-slot:cell(status)="data">
                  <span
                    class="badge badge-soft-success"
                    :class="{
                      'badge-soft-danger': data.item.status === 'Deactive',
                    }"
                    >{{ data.item.status }}</span
                  >
                </template>
                <template v-slot:cell(rating)="data">
                  <span
                    class="badge"
                    :class="{
                      'bg-success': data.item.rating >= 4,
                      'bg-danger': data.item.rating < 3,
                      'bg-warning':
                        data.item.rating > 3 && data.item.rating < 4,
                    }"
                    ><i class="mdi mdi-star"></i> {{ data.item.rating }}</span
                  >
                </template>
                <template v-slot:cell(action)>
                  <ul class="list-inline table-action m-0">
                    <li class="list-inline-item">
                      <a href="javascript:void(0);" class="action-icon">
                        <i class="mdi mdi-eye"></i
                      ></a>
                    </li>
                    <li class="list-inline-item">
                      <a href="javascript:void(0);" class="action-icon">
                        <i class="mdi mdi-square-edit-outline"></i
                      ></a>
                    </li>
                    <li class="list-inline-item">
                      <a href="javascript:void(0);" class="action-icon">
                        <i class="mdi mdi-delete"></i
                      ></a>
                    </li>
                  </ul>
                </template>
              </b-table>
            </div>
            <div class="row">
              <div class="col">
                <div
                  class="dataTables_paginate paging_simple_numbers float-end"
                >
                  <ul class="pagination pagination-rounded">
                    <!-- pagination -->
                    <b-pagination
                      v-model="currentPage"
                      :total-rows="rows"
                      :per-page="perPage"
                    ></b-pagination>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </Layout>
</template>
