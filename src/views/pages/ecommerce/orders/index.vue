<script>
import { ordersData } from "./data";
import Layout from "../../../layouts/main";
import PageHeader from "@/components/Page-header";
import appConfig from "../../../../../app.config";

/**
 * Orders component
 */
export default {
  components: {
    Layout,
    PageHeader,
  },
  page: {
    title: "Orders",
    meta: [{ name: "description", content: appConfig.description }],
  },
  data() {
    return {
      ordersData: ordersData,
      title: "Orders",
      items: [
        {
          text: "Minton",
        },
        {
          text: "eCommerce",
        },
        {
          text: "Orders",
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
          key: "id",
          label: "Order ID",
        },
        {
          key: "name",
          label: "Billing Name",
        },
        {
          key: "date",
          label: "Last Order",
        },
        {
          key: "status",
          label: "Payment Status",
        },
        {
          key: "total",
        },
        {
          key: "payment",
          label: "Payment Method",
        },
        {
          key: "orderstatus",
          label: "Order Status",
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
      return this.ordersData.length;
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
              <div class="col-lg-8">
                <form class="d-flex flex-wrap align-items-center">
                  <div class="d-flex flex-wrap align-items-center mb-2">
                    <label for="inputPassword2" class="visually-hidden"
                      >Search</label
                    >
                    <input
                      type="search"
                      class="form-control"
                      id="inputPassword2"
                      placeholder="Search..."
                    />
                  </div>
                  <div class="d-flex flex-wrap align-items-center mx-sm-3 mb-2">
                    <label for="status-select" class="me-2">Status</label>
                    <div>
                      <select class="form-select" id="status-select">
                        <option selected="">Choose...</option>
                        <option value="1">Paid</option>
                        <option value="2">Awaiting Authorization</option>
                        <option value="3">Payment failed</option>
                        <option value="4">Cash On Delivery</option>
                        <option value="5">Fulfilled</option>
                        <option value="6">Unfulfilled</option>
                      </select>
                    </div>
                  </div>
                </form>
              </div>
              <div class="col-lg-4">
                <div class="text-lg-end">
                  <button type="button" class="btn btn-danger mb-2 me-2">
                    <i class="mdi mdi-basket me-1"></i> Add New Order
                  </button>
                  <button type="button" class="btn btn-light mb-2">
                    Export
                  </button>
                </div>
              </div>
              <!-- end col-->
            </div>
            <!-- Table -->
            <div class="table-responsive datatables mb-0">
              <b-table
                table-class="table table-centered w-100"
                thead-tr-class="table-light"
                :items="ordersData"
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
                  <div class="custom-control custom-checkbox text-center">
                    <input
                      type="checkbox"
                      class="form-check-input"
                      :id="`contacusercheck${data.item.id}`"
                    />
                    <label
                      class="form-check-label"
                      :for="`contacusercheck${data.item.id}`"
                    ></label>
                  </div>
                </template>

                <template v-slot:cell(id)="data">
                  <router-link
                    to="/ecommerce/order-detail"
                    class="text-body fw-medium"
                    >{{ data.item.id }}</router-link
                  >
                </template>
                <template v-slot:cell(status)="data">
                  <span
                    class="badge badge-soft-success"
                    :class="{
                      'badge-soft-warning':
                        data.item.status === 'Awaiting Authorization',
                      'badge-soft-danger':
                        data.item.status === 'Payment Failed',
                    }"
                  >
                    {{ data.item.status }}</span
                  >
                </template>
                <template v-slot:cell(name)="data">
                  {{ data.item.name }}
                </template>
                <template v-slot:cell(date)="data">
                  {{ data.item.date }}
                  <small class="text-muted">{{ data.item.time }}</small>
                </template>
                <template v-slot:cell(payment)="data">
                  {{ data.item.payment }}
                </template>
                <template v-slot:cell(orderstatus)="data">
                  <span
                    class="badge"
                    :class="{
                      'bg-warning': data.item.orderstatus === 'Processing',
                      'bg-success': data.item.orderstatus === 'Delivered',
                      'bg-info': data.item.orderstatus === 'Shipped',
                      'bg-danger': data.item.orderstatus === 'Cancelled',
                    }"
                  >
                    {{ data.item.orderstatus }}</span
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
