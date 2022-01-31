<script>
export default {};
</script>

<template>
  <div class="card">
    <div class="card-body">
      <div class="clearfix">
        <a href="" class="p-0 float-end mb-3"
          >Export <i class="mdi mdi-download ms-1"></i
        ></a>
        <h4 class="header-title mt-1">Social Media Traffic</h4>
      </div>
      <div class="table-responsive mb-0">
        <table class="table table-sm table-centered mb-0 font-14">
          <thead class="table-light">
            <tr>
              <th>Network</th>
              <th>Visits</th>
              <th style="width: 40%;"></th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Facebook</td>
              <td>2,250</td>
              <td>
                <div class="progress" style="height: 3px;">
                  <div
                    class="progress-bar"
                    role="progressbar"
                    style="width: 65%;"
                    aria-valuenow="65"
                    aria-valuemin="0"
                    aria-valuemax="100"
                  ></div>
                </div>
              </td>
            </tr>
            <tr>
              <td>Instagram</td>
              <td>1,501</td>
              <td>
                <div class="progress" style="height: 3px;">
                  <div
                    class="progress-bar"
                    role="progressbar"
                    style="width: 45%;"
                    aria-valuenow="45"
                    aria-valuemin="0"
                    aria-valuemax="100"
                  ></div>
                </div>
              </td>
            </tr>
            <tr>
              <td>Twitter</td>
              <td>750</td>
              <td>
                <div class="progress" style="height: 3px;">
                  <div
                    class="progress-bar"
                    role="progressbar"
                    style="width: 30%;"
                    aria-valuenow="30"
                    aria-valuemin="0"
                    aria-valuemax="100"
                  ></div>
                </div>
              </td>
            </tr>
            <tr>
              <td>LinkedIn</td>
              <td>540</td>
              <td>
                <div class="progress" style="height: 3px;">
                  <div
                    class="progress-bar"
                    role="progressbar"
                    style="width: 25%;"
                    aria-valuenow="25"
                    aria-valuemin="0"
                    aria-valuemax="100"
                  ></div>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
      <!-- end table-responsive-->
    </div>
    <!-- end card-body-->
  </div>
  <!-- end card-->
</template>
