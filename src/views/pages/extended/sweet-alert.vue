<script>
import Swal from "sweetalert2";

import Layout from "../../layouts/main";
import PageHeader from "@/components/Page-header";
import appConfig from "../../../../app.config";

/**
 * Sweet-alert component
 */
export default {
  page: {
    title: "Sweet-alert",
    meta: [{ name: "description", content: appConfig.description }],
  },
  components: {
    Layout,
    PageHeader,
  },
  data() {
    return {
      title: "Sweet Alerts",
      items: [
        {
          text: "Minton",
          href: "/",
        },
        {
          text: "Extended UI",
          href: "/",
        },
        {
          text: "Sweet Alerts",
          active: true,
        },
      ],
    };
  },
  methods: {
    showAlert() {
      Swal.fire({
        title: "Any fool can use a computer!",
        confirmButtonColor: "#3bafda",
      });
    },
    titleText() {
      Swal.fire({
        title: "The Internet?",
        text: "That thing is still around?",
        icon: "question",
        confirmButtonColor: "#3bafda",
      });
    },
    successmsg() {
      Swal.fire({
        title: "Good job!",
        text: "You clicked the button!",
        icon: "success",
        showCancelButton: true,
        confirmButtonColor: "#3bafda",
        cancelButtonColor: "#f1556c",
      });
    },
    content() {
      Swal.fire({
        imageUrl: "https://placeholder.pics/svg/300x1500",
        imageHeight: 1500,
        imageAlt: "A tall image",
        confirmButtonColor: "#3bafda",
      });
    },
    position() {
      Swal.fire({
        position: "top-end",
        icon: "success",
        title: "Your work has been saved",
        showConfirmButton: false,
        timer: 1500,
      });
    },
    errorIcon() {
      Swal.fire({
        icon: "error",
        title: "Oops...",
        text: "Something went wrong!",
        footer: "<a>Why do I have this issue?</a>",
      });
    },
    confirm() {
      Swal.fire({
        title: "Are you sure?",
        text: "You won't be able to revert this!",
        icon: "warning",
        showCancelButton: true,
        confirmButtonColor: "#1abc9c",
        cancelButtonColor: "#f1556c",
        confirmButtonText: "Yes, delete it!",
      }).then(function (result) {
        if (result.value) {
          Swal.fire({
            title: "Deleted!",
            text: "Your file has been deleted.",
            icon: "success",
            confirmButtonColor: "#1abc9c",
          });
        }
      });
    },
    cancel() {
      Swal.fire({
        title: "Are you sure?",
        text: "You won't be able to revert this!",
        icon: "warning",
        showCancelButton: true,
        confirmButtonText: "Yes, delete it!",
        cancelButtonText: "No, cancel!",
        confirmButtonColor: "#1abc9c",
        cancelButtonColor: "#f1556c"
      }).then((result) => {
        if (result.value) {
          Swal.fire({
            title: "Deleted!",
            text: "Your file has been deleted.",
            icon: "success",
            confirmButtonColor: "#1abc9c",
          });
        } else {
          Swal.fire({
            title: "Cancelled",
            text: "Your imaginary file is safe :)",
            icon: "error",
            confirmButtonColor: "#1abc9c",
          });
        }
      });
    },
    imageHeader() {
      Swal.fire({
        title: "Minton",
        text: "Responsive Bootstrap 5 Admin Dashboard",
        imageUrl: require("@/assets/images/logo-sm-dark.png"),
        imageHeight: 50,
        confirmButtonColor: "#3bafda",
      });
    },
    timer() {
      var timerInterval;
      Swal.fire({
        title: "Auto close alert!",
        html: "I will close in <strong></strong> seconds.",
        timer: 2000,
        confirmButtonColor: "#3bafda",
        willOpen: () => {
          Swal.showLoading();
          timerInterval = setInterval(() => {
            Swal.getContent().querySelector("strong").textContent =
              Swal.getTimerLeft() + "";
          }, 100);
        },
        willClose: () => {
          clearInterval(timerInterval);
        },
      }).then((result) => {
        if (result.dismiss === Swal.DismissReason.timer) {
          console.log("I was closed by the timer");
        }
      });
    },
    custom() {
      Swal.fire({
        title: "<i>HTML</i> <u>example</u>",
        icon: "info",
        html:
          "You can use <b>Minton text</b>, " +
          '<a href="//coderthemes.com/">links</a> ' +
          "and other HTML tags",
        showCloseButton: true,
        showCancelButton: true,
        confirmButtonColor: "#1abc9c",
        cancelButtonColor: "#f1556c",
        confirmButtonText: '<i class="mdi mdi-thumb-up-outline"></i> Great!',
        cancelButtonText: '<i class="mdi mdi-thumb-down-outline"></i>',
      });
    },
    customBackground() {
      Swal.fire({
        title: "Custom width, padding, background.",
        width: 600,
        padding: 100,
        confirmButtonColor: "#3bafda",
        background:
          "#fff url(//subtlepatterns2015.subtlepatterns.netdna-cdn.com/patterns/geometry.png)",
      });
    },
    ajax() {
      Swal.fire({
        title: "Submit your Github username",
        input: "text",
        inputAttributes: {
          autocapitalize: "off",
        },
        showCancelButton: true,
        confirmButtonText: "Look up",
        showLoaderOnConfirm: true,
        confirmButtonColor: "#3bafda",
        cancelButtonColor: "#f1556c",
        preConfirm: (login) => {
          return fetch(`//api.github.com/users/${login}`)
            .then((response) => {
              if (!response.ok) {
                throw new Error(response.statusText);
              }
              return response.json();
            })
            .catch((error) => {
              Swal.showValidationMessage(`Request failed: ${error}`);
            });
        },
        allowOutsideClick: () => !Swal.isLoading(),
      }).then((result) => {
        if (result.value) {
          Swal.fire({
            title: `${result.value.login}'s avatar`,
            imageUrl: result.value.avatar_url,
            confirmButtonColor: "#1abc9c",
          });
        }
      });
    },
    chain() {
      Swal.mixin({
        input: "text",
        confirmButtonText: "Next &rarr;",
        showCancelButton: true,
        confirmButtonColor: "#3bafda",
        cancelButtonColor: "#f1556c",
        progressSteps: ["1", "2", "3"],
      })
        .queue([
          {
            title: "Question 1",
            text: "Chaining swal2 modals is easy",
          },
          "Question 2",
          "Question 3",
        ])
        .then((result) => {
          if (result.value) {
            Swal.fire({
              title: "All done!",
              html:
                "Your answers: <pre><code>" +
                JSON.stringify(result.value) +
                "</code></pre>",
              confirmButtonText: "Lovely!",
              confirmButtonColor: "#3bafda",
            });
          }
        });
    },
    dynamicQueue() {
      var ipAPI = "https://api.ipify.org?format=json";
      Swal.queue([
        {
          title: "Your public IP",
          confirmButtonColor: "#1abc9c",
          confirmButtonText: "Show my public IP",
          text: "Your public IP will be received " + "via AJAX request",
          showLoaderOnConfirm: true,
          preConfirm: () => {
            return fetch(ipAPI)
              .then((response) => response.json())
              .then((data) => Swal.insertQueueStep(data.ip))
              .catch(() => {
                Swal.insertQueueStep({
                  icon: "error",
                  title: "Unable to get your public IP",
                });
              });
          },
        },
      ]);
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
            <h4 class="header-title">Examples</h4>

            <p class="sub-header">
              A beautiful, responsive, customizable, accessible (WAI-ARIA)
              replacement for JavaScript's popup boxes
            </p>

            <table class="table table-borderless table-centered mb-0">
              <thead class="table-light">
                <tr>
                  <th style="width: 50%">Alert Type</th>
                  <th>Example</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>A basic message</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="showAlert"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>A title with a text under</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="titleText"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>A success message!</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="successmsg"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>A modal window with a long content inside:</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="content"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>A custom positioned dialog</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="position"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>
                    A modal with a title, an error icon, a text, and a footer
                  </td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="errorIcon"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>
                    A confirm dialog, with a function attached to the
                    "Confirm"-button...
                  </td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="confirm"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>
                    By passing a parameter, you can execute something else for
                    "Cancel".
                  </td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="cancel"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>A message with custom Image Header</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="imageHeader"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>A message with auto close timer</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="timer"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>Custom HTML description and buttons</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="custom"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>A message with custom width, padding and background</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="customBackground"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>Ajax request example</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="ajax"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>Chaining modals (queue) example</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="chain"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
                <tr>
                  <td>Dynamic queue example</td>
                  <td>
                    <button
                      id="sa-basic"
                      type="button"
                      class="btn btn-info btn-xs"
                      @click="dynamicQueue"
                    >
                      Click me
                    </button>
                  </td>
                </tr>
              </tbody>
            </table>
            <!-- end table -->
          </div>
        </div>
      </div>
      <!--end col -->
    </div>
    <!-- end row -->
  </Layout>
</template>
