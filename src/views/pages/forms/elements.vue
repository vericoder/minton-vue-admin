<script>
import Layout from "../../layouts/main";
import PageHeader from "@/components/Page-header";
import appConfig from "../../../../app.config";

/**
 * Form elements component
 */
export default {
  page: {
    title: "Form elements",
    meta: [{ name: "description", content: appConfig.description }],
  },
  components: {
    Layout,
    PageHeader,
  },
  data() {
    return {
      title: "Form Elements",
      items: [
        {
          text: "Minton",
          href: "/",
        },
        {
          text: "Forms",
          href: "/",
        },
        {
          text: "Form Elements",
          active: true,
        },
      ],
      checked: true,
      checked2: false,
      status: "accepted",
      status2: "not_accepted",
      selected: "A",
    };
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
            <h4 class="header-title">Input Types</h4>
            <p class="sub-header">
              Most common form control, text-based input fields. Includes
              support for all HTML5 types:
              <code>text</code>, <code>password</code>, <code>datetime</code>,
              <code>datetime-local</code>, <code>date</code>,
              <code>month</code>, <code>time</code>, <code>week</code>,
              <code>number</code>, <code>email</code>, <code>url</code>,
              <code>search</code>, <code>tel</code>, and <code>color</code>.
            </p>

            <div class="row">
              <div class="col-12">
                <div class="p-2">
                  <form class="form-horizontal" role="form">
                    <b-form-group
                      class="mb-2"
                      id="example text"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="Text"
                      label-for="text"
                    >
                      <b-form-input
                        for="text"
                        value="Some text value..."
                      ></b-form-input>
                    </b-form-group>

                    <b-form-group
                      class="mb-2"
                      id="example-email"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="Email"
                      label-for="email"
                    >
                      <b-form-input
                        id="email"
                        placeholder="Email"
                      ></b-form-input>
                    </b-form-group>
                    <b-form-group
                      class="mb-2"
                      id="example-password"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="Password"
                      label-for="pwd"
                    >
                      <b-form-input
                        id="pwd"
                        type="password"
                        value="password"
                      ></b-form-input>
                    </b-form-group>
                    <b-form-group
                      class="mb-2"
                      id="example-password"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="Show/Hide Password"
                      label-for="pwd2"
                    >
                      <div class="input-group input-group-merge">
                        <b-form-input
                          id="pwd2"
                          type="password"
                          placeholder="Enter your password"
                        ></b-form-input>
                        <div class="input-group-text" data-password="false">
                          <span class="password-eye"></span>
                        </div>
                      </div>
                    </b-form-group>

                    <b-form-group
                      class="mb-2"
                      id="example-placeholder"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="Placeholder"
                      label-for="placeholder"
                    >
                      <b-form-input
                        id="placeholder"
                        type="password"
                        placeholder="placeholder"
                      ></b-form-input>
                    </b-form-group>
                    <b-form-group
                      class="mb-2"
                      id="example-textarea"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="textarea"
                      label-for="textarea"
                    >
                      <b-form-textarea id="textarea" rows="4"></b-form-textarea>
                    </b-form-group>

                    <b-form-group
                      class="mb-2"
                      id="example-textarea"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="Readonly"
                      label-for="Readonly"
                    >
                      <b-form-input
                        id="Readonly"
                        value="Readonly value"
                        readonly
                      ></b-form-input>
                    </b-form-group>

                    <b-form-group
                      class="mb-2"
                      id="example-textarea"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="Disabled"
                      label-for="Disabled"
                    >
                      <b-form-input
                        id="Disabled"
                        value="Disabled value"
                        disabled
                      ></b-form-input>
                    </b-form-group>

                    <b-form-group
                      class="mb-2"
                      id="example-textarea"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="Static control"
                      label-for="static"
                    >
                      <b-form-input
                        id="static"
                        value="email@example.com"
                        plaintext
                      ></b-form-input>
                    </b-form-group>

                    <b-form-group
                      class="mb-2"
                      id="input-group-1"
                      label-cols-sm="2"
                      label-cols-lg="2"
                      label="Helping text"
                      label-for="example-helping"
                      description="A block of help text that breaks onto a new line
                            and may extend beyond one line."
                    >
                      <b-form-input
                        id="example-helping"
                        type="email"
                        placeholder="Helping text"
                        required
                      ></b-form-input>
                    </b-form-group>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label"
                        >Input Select</label
                      >
                      <div class="col-md-10">
                        <select class="form-control">
                          <option>1</option>
                          <option>2</option>
                          <option>3</option>
                          <option>4</option>
                          <option>5</option>
                        </select>
                        <h6>Multiple select</h6>
                        <select multiple class="form-control">
                          <option>1</option>
                          <option>2</option>
                          <option>3</option>
                          <option>4</option>
                          <option>5</option>
                        </select>
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label
                        class="col-md-2 col-form-label"
                        for="example-fileinput"
                        >Default file input</label
                      >
                      <div class="col-md-10">
                        <input
                          type="file"
                          class="form-control"
                          id="example-fileinput"
                        />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label" for="example-date"
                        >Date</label
                      >
                      <div class="col-md-10">
                        <input
                          class="form-control"
                          type="date"
                          name="date"
                          id="example-date"
                        />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label" for="example-month"
                        >Month</label
                      >
                      <div class="col-md-10">
                        <input
                          class="form-control"
                          type="month"
                          id="example-month"
                          name="month"
                        />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label" for="example-time"
                        >Time</label
                      >
                      <div class="col-md-10">
                        <input
                          class="form-control"
                          type="time"
                          id="example-time"
                          name="time"
                        />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label" for="example-week"
                        >Week</label
                      >
                      <div class="col-md-10">
                        <input
                          class="form-control"
                          type="week"
                          id="example-week"
                          name="week"
                        />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label
                        class="col-md-2 col-form-label"
                        for="example-number"
                        >Number</label
                      >
                      <div class="col-md-10">
                        <input
                          class="form-control"
                          type="number"
                          id="example-number"
                          name="number"
                        />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label">URL</label>
                      <div class="col-md-10">
                        <input class="form-control" type="url" name="url" />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label">Search</label>
                      <div class="col-md-10">
                        <input
                          class="form-control"
                          type="search"
                          name="search"
                        />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label">Tel</label>
                      <div class="col-md-10">
                        <input class="form-control" type="tel" name="tel" />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label" for="example-color"
                        >Color</label
                      >
                      <div class="col-md-10">
                        <input
                          class="form-control form-control-color mw-100"
                          type="color"
                          id="example-color"
                          name="color"
                          value="#3bafda"
                        />
                      </div>
                    </div>

                    <div class="mb-2 row">
                      <label class="col-md-2 col-form-label" for="form-range"
                        >Form range</label
                      >
                      <div class="col-md-10 align-self-center">
                        <input
                          class="form-range"
                          type="range"
                          id="form-range"
                          name="range"
                          min="0"
                          max="10"
                        />
                      </div>
                    </div>

                    <div class="row">
                      <label
                        for="exampleDataList"
                        class="col-md-2 col-form-label"
                        >Datalists</label
                      >
                      <div class="col-md-10">
                        <input
                          class="form-control"
                          list="datalistOptions"
                          id="exampleDataList"
                          placeholder="Type to search..."
                        />
                        <datalist id="datalistOptions">
                          <option value="San Francisco"></option>
                          <option value="New York"></option>
                          <option value="Seattle"></option>
                          <option value="Los Angeles"></option>
                          <option value="Chicago"></option>
                        </datalist>
                      </div>
                    </div>
                  </form>
                </div>
              </div>
            </div>
            <!-- end row -->
          </div>
          <!-- end card-body -->
        </div>
      </div>
      <!-- end col -->
    </div>
    <!-- end row -->

    <div class="row">
      <div class="col-12">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Select Menu</h4>
            <p class="sub-header">
              Custom <code>&lt;select&gt;</code> menus need only a custom class,
              <code>.form-select</code> to trigger the custom styles.
            </p>

            <select class="form-select">
              <option selected>Open this select menu</option>
              <option value="1">One</option>
              <option value="2">Two</option>
              <option value="3">Three</option>
            </select>

            <div class="mt-4">
              <h5 class="font-14 mb-1">Select Menu Sizing</h5>
              <p class="sub-header mb-0">
                You may also choose from small and large custom selects to match
                our similarly sized text inputs.
              </p>

              <div class="row">
                <div class="col-lg-6">
                  <div class="mt-3">
                    <label class="form-label">Large Form Select</label>
                    <select
                      class="form-select form-select-lg"
                      aria-label=".form-select-lg example"
                    >
                      <option selected>Open this select menu</option>
                      <option value="1">One</option>
                      <option value="2">Two</option>
                      <option value="3">Three</option>
                    </select>
                  </div>
                </div>

                <div class="col-lg-6">
                  <div class="mt-3">
                    <label class="form-label">Small Form Select</label>
                    <select
                      class="form-select form-select-sm"
                      aria-label=".form-select-sm example"
                    >
                      <option selected>Open this select menu</option>
                      <option value="1">One</option>
                      <option value="2">Two</option>
                      <option value="3">Three</option>
                    </select>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- end card -->
      </div>
      <!-- end col -->
    </div>
    <!-- end row -->

    <div class="row">
      <div class="col-12">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Checkboxes & radios</h4>

            <div class="row">
              <div class="col-md-6">
                <div class="mt-3">
                  <h5 class="font-14 mb-2">Checkbox</h5>

                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="flexCheckDefault"
                    />
                    <label class="form-check-label" for="flexCheckDefault">
                      Default checkbox
                    </label>
                  </div>
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="flexCheckChecked"
                      checked
                    />
                    <label class="form-check-label" for="flexCheckChecked">
                      Checked checkbox
                    </label>
                  </div>
                </div>
              </div>

              <div class="col-md-6">
                <div class="mt-3">
                  <h5 class="font-14 mb-2">Radios</h5>

                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="radio"
                      name="flexRadioDefault"
                      id="flexRadioDefault1"
                    />
                    <label class="form-check-label" for="flexRadioDefault1">
                      Default radio
                    </label>
                  </div>
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="radio"
                      name="flexRadioDefault"
                      id="flexRadioDefault2"
                      checked
                    />
                    <label class="form-check-label" for="flexRadioDefault2">
                      Default checked radio
                    </label>
                  </div>

                  <div class="custom-control custom-radio">
                    <input
                      type="radio"
                      id="customRadio1"
                      name="customRadio"
                      class="custom-control-input"
                    />
                    <label class="custom-control-label" for="customRadio1"
                      >Toggle this custom radio</label
                    >
                  </div>
                </div>
              </div>
            </div>

            <div>
              <h4 class="header-title mt-4">Switches</h4>
              <p class="sub-header">
                A switch has the markup of a custom checkbox but uses the
                <code>.form-switch</code> class to render a toggle switch.
                Switches also support the <code>disabled</code> attribute.
              </p>

              <div class="form-check form-switch">
                <input
                  class="form-check-input"
                  type="checkbox"
                  id="flexSwitchCheckDefault"
                />
                <label class="form-check-label" for="flexSwitchCheckDefault"
                  >Default switch checkbox input</label
                >
              </div>
              <div class="form-check form-switch">
                <input
                  class="form-check-input"
                  type="checkbox"
                  id="flexSwitchCheckChecked"
                  checked
                />
                <label class="form-check-label" for="flexSwitchCheckChecked"
                  >Checked switch checkbox input</label
                >
              </div>
              <div class="form-check form-switch">
                <input
                  class="form-check-input"
                  type="checkbox"
                  id="flexSwitchCheckDisabled"
                  disabled
                />
                <label class="form-check-label" for="flexSwitchCheckDisabled"
                  >Disabled switch checkbox input</label
                >
              </div>
              <div class="form-check form-switch">
                <input
                  class="form-check-input"
                  type="checkbox"
                  id="flexSwitchCheckCheckedDisabled"
                  checked
                  disabled
                />
                <label
                  class="form-check-label"
                  for="flexSwitchCheckCheckedDisabled"
                  >Disabled checked switch checkbox input</label
                >
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- end card -->
    </div>
    <!-- end row -->

    <div class="row">
      <div class="col-12">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Input Sizes & Group</h4>
            <p class="sub-header">
              Set heights using classes like
              <code>.input-lg</code>, and set widths using grid column classes
              like <code>.col-lg-*</code>.
            </p>

            <div class="p-2">
              <form role="form" class="form-horizontal">
                <b-form-group
                  class="mb-3"
                  label-cols="4"
                  label-cols-lg="2"
                  label-size="sm"
                  label="Small"
                  label-for="input-small"
                >
                  <b-form-input
                    type="text"
                    id="input-small"
                    size="sm"
                    placeholder="sm"
                  ></b-form-input>
                </b-form-group>

                <b-form-group
                  class="mb-3"
                  label-cols="4"
                  label-cols-lg="2"
                  label="Default"
                  label-for="input-default"
                >
                  <b-form-input
                    type="text"
                    id="input-default"
                    placeholder="Normal"
                  ></b-form-input>
                </b-form-group>

                <b-form-group
                  class="mb-3"
                  label-cols="4"
                  label-cols-lg="2"
                  label-size="lg"
                  label="Large"
                  label-for="input-lg"
                >
                  <b-form-input
                    type="text"
                    id="input-lg"
                    size="lg"
                    placeholder="lg"
                  ></b-form-input>
                </b-form-group>

                <div class="mb-3 row">
                  <label class="col-sm-2 col-form-label">Grid Sizes</label>
                  <div class="col-sm-4">
                    <input
                      type="text"
                      class="form-control"
                      placeholder=".col-sm-4"
                    />
                  </div>
                </div>

                <div class="mb-3 row">
                  <label class="col-sm-2 col-form-label">Static</label>
                  <div class="col-sm-10">
                    <b-input-group prepend="@" class="me-sm-2 mb-sm-0">
                      <b-input
                        id="inline-form-input-username"
                        placeholder="Username"
                      ></b-input>
                    </b-input-group>
                  </div>
                </div>

                <div class="mb-3 row">
                  <label class="col-sm-2 col-form-label">Dropdowns</label>
                  <div class="col-sm-10">
                    <div class="input-group">
                      <b-dropdown class="input-group-prepend" variant="primary">
                        <template v-slot:button-content>
                          Dropdown
                          <i class="mdi mdi-chevron-down"></i>
                        </template>
                        <a class="dropdown-item" href="#">Action</a>
                        <a class="dropdown-item" href="#">Another action</a>
                        <a class="dropdown-item" href="#"
                          >Something else here</a
                        >
                        <div role="separator" class="dropdown-divider"></div>
                        <a class="dropdown-item" href="#">Separated link</a>
                      </b-dropdown>
                      <input
                        type="text"
                        class="form-control"
                        placeholder
                        aria-label
                        aria-describedby="basic-addon1"
                      />
                    </div>
                  </div>
                </div>

                <div class="form-group row mb-0">
                  <label class="col-sm-2 col-form-label">Buttons</label>
                  <div class="col-sm-10">
                    <div class="input-group">
                      <input
                        type="text"
                        class="form-control"
                        placeholder="Recipient's username"
                        aria-label="Recipient's username"
                        aria-describedby="basic-addon2"
                      />
                      <div class="input-group-append">
                        <button
                          class="btn btn-dark"
                          type="button"
                        >
                          Button
                        </button>
                      </div>
                    </div>
                  </div>
                </div>
              </form>
            </div>
          </div>
          <!-- end card-body -->
        </div>
      </div>
      <!-- end col -->
    </div>
    <!-- end row -->

    <div class="row">
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title mb-3">Basic Example</h4>

            <form role="form">
              <b-form-group
                class="mb-2"
                id="fieldset-1"
                description="We'll never share your email with anyone else."
                label="Email address"
                label-for="exampleInputEmail1"
                label-class="form-label"
              >
                <b-form-input
                  id="exampleInputEmail1"
                  type="email"
                  placeholder="Enter email"
                ></b-form-input>
              </b-form-group>
              <b-form-group
                class="mb-2"
                label="Password"
                label-class="form-label"
                label-for="exampleInputPassword1"
              >
                <b-form-input
                  id="exampleInputPassword1"
                  type="password"
                  placeholder="Password"
                ></b-form-input>
              </b-form-group>
              <div class="mb-2 form-check">
                <input
                  type="checkbox"
                  class="form-check-input"
                  id="exampleCheck1"
                />
                <label class="form-check-label" for="exampleCheck1"
                  >Check me out</label
                >
              </div>
              <b-button type="submit" variant="primary">Submit</b-button>
            </form>
          </div>
        </div>
      </div>
      <!-- end col -->

      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title mb-3">Horizontal form</h4>

            <form class="form-horizontal" role="form">
              <b-form-group
                class="mb-3"
                label-cols-sm="4"
                label-cols-lg="3"
                label="Email"
                label-for="inputEmail3"
              >
                <b-form-input
                  type="email"
                  id="inputEmail3"
                  placeholder="Email"
                ></b-form-input>
              </b-form-group>
              <b-form-group
                class="mb-3"
                label-cols-sm="4"
                label-cols-lg="3"
                label="Password"
                label-for="inputPassword6"
              >
                <b-form-input
                  type="password"
                  id="inputPassword6"
                  placeholder="Password"
                ></b-form-input>
              </b-form-group>
              <b-form-group
                class="mb-2"
                label-cols-sm="4"
                label-cols-lg="3"
                label="Re Password"
                label-for="inputPassword5"
              >
                <b-form-input
                  type="password"
                  id="inputPassword5"
                  placeholder="Retype Password"
                ></b-form-input>
              </b-form-group>

              <div class="mb-2 row justify-content-end">
                <div class="col-sm-9">
                  <div class="form-check">
                    <input
                      type="checkbox"
                      class="form-check-input"
                      id="checkmeout"
                    />
                    <label class="form-check-label" for="checkmeout"
                      >Check me out</label
                    >
                  </div>
                </div>
              </div>
              <div class="form-group mb-0 justify-content-end row">
                <div class="col-sm-9">
                  <b-button variant="info" type="submit">Sign in</b-button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
    <!-- end row -->

    <!-- Inline Form -->
    <div class="row">
      <div class="col-md-12">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Inline Form</h4>
            <p class="sub-header">
              Use the <code>.col-auto</code> class to create horizontal layouts.
            </p>
            <form class="row row-cols-lg-auto g-3 align-items-center">
              <div class="col-12">
                <label for="staticEmail2" class="visually-hidden">Email</label>
                <b-form-input
                  type="text"
                  plaintext
                  id="staticEmail2"
                  value="email@example.com"
                ></b-form-input>
              </div>
              <div class="col-12">
                <label for="inputPassword3" class="visually-hidden"
                  >Password</label
                >
                <input
                  type="password"
                  class="form-control"
                  id="inputPassword3"
                  placeholder="Password"
                />
              </div>
              <button type="submit" class="btn btn-primary">
                Confirm identity
              </button>
            </form>

            <div class="row">
              <h6 class="font-13 mt-4">Auto-sizing</h6>

              <form>
                <div class="row gy-2 gx-3 align-items-center">
                  <div class="col-auto">
                    <label class="visually-hidden" for="inlineFormInput"
                      >Name</label
                    >
                    <input
                      type="text"
                      class="form-control"
                      id="inlineFormInput"
                      placeholder="Jane Doe"
                    />
                  </div>
                  <div class="col-auto">
                    <label class="visually-hidden" for="inlineFormInputGroup"
                      >Username</label
                    >
                    <div class="input-group">
                      <div class="input-group-text">@</div>
                      <input
                        type="text"
                        class="form-control"
                        id="inlineFormInputGroup"
                        placeholder="Username"
                      />
                    </div>
                  </div>
                  <div class="col-auto">
                    <div class="form-check">
                      <input
                        class="form-check-input"
                        type="checkbox"
                        id="autoSizingCheck"
                      />
                      <label class="form-check-label" for="autoSizingCheck">
                        Remember me
                      </label>
                    </div>
                  </div>
                  <div class="col-auto">
                    <button type="submit" class="btn btn-primary">
                      Submit
                    </button>
                  </div>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- end row -->

    <!-- Form row -->
    <div class="row">
      <div class="col-xl-6">
        <div class="card">
          <div class="card-body">
            <h4 class="header-title">Form grid</h4>
            <p class="sub-header">
              You may also swap <code>.row</code> for <code>.row</code>, a
              variation of our standard grid row that overrides the default
              column gutters for tighter and more compact layouts.
            </p>

            <form>
              <div class="row">
                <div class="mb-2 col-md-6">
                  <label for="inputEmail4" class="form-label">Email</label>
                  <input
                    type="email"
                    class="form-control"
                    id="inputEmail4"
                    placeholder="Email"
                  />
                </div>
                <div class="mb-2 col-md-6">
                  <label for="inputPassword4" class="form-label"
                    >Password</label
                  >
                  <input
                    type="password"
                    class="form-control"
                    id="inputPassword4"
                    placeholder="Password"
                  />
                </div>
              </div>
              <div class="mb-2">
                <label for="inputAddress" class="form-label">Address</label>
                <input
                  type="text"
                  class="form-control"
                  id="inputAddress"
                  placeholder="1234 Main St"
                />
              </div>

              <div class="row">
                <div class="mb-2 col-md-4">
                  <label for="inputState" class="form-label">State</label>
                  <select id="inputState" class="form-select">
                    <option>Choose</option>
                    <option>Option 1</option>
                    <option>Option 2</option>
                    <option>Option 3</option>
                  </select>
                </div>

                <div class="mb-2 col-md-4">
                  <label for="inputCity" class="form-label">City</label>
                  <input type="text" class="form-control" id="inputCity" />
                </div>

                <div class="mb-2 col-md-4">
                  <label for="inputZip" class="form-label">Zip</label>
                  <input type="text" class="form-control" id="inputZip" />
                </div>
              </div>
              <div class="mb-3">
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" id="Check" />
                  <label class="form-check-label" for="Check">
                    Check me out
                  </label>
                </div>
              </div>
              <button type="submit" class="btn btn-primary">Sign in</button>
            </form>
          </div>
        </div>
      </div>
      <!-- end col -->

      <div class="col-xl-6">
        <div class="card">
          <div class="card-body">
            <h5 class="header-title">Floating labels</h5>
            <p class="sub-header">
              Create beautifully simple form labels that float over your input
              fields.
            </p>

            <form>
              <div class="form-floating mb-3">
                <input
                  type="text"
                  class="form-control"
                  id="floatingnameInput"
                  placeholder="Enter Name"
                  value="Nik Patel"
                />
                <label for="floatingnameInput">Name</label>
              </div>
              <div class="row">
                <div class="col-md-6">
                  <div class="form-floating mb-3">
                    <input
                      type="email"
                      class="form-control"
                      id="floatingemailInput"
                      placeholder="Enter Email address"
                      value="name@example.com"
                    />
                    <label for="floatingemailInput">Email address</label>
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-floating mb-3">
                    <select
                      class="form-select"
                      id="floatingSelectGrid"
                      aria-label="Floating label select example"
                    >
                      <option selected>Open this select menu</option>
                      <option value="1">One</option>
                      <option value="2">Two</option>
                      <option value="3">Three</option>
                    </select>
                    <label for="floatingSelectGrid">Works with selects</label>
                  </div>
                </div>
              </div>

              <div class="form-floating mb-2">
                <textarea
                  class="form-control"
                  placeholder="Leave a comment here"
                  id="floatingTextarea"
                  style="height: 100px"
                >
123, Main st</textarea
                >
                <label for="floatingTextarea">Comments</label>
              </div>

              <div class="mb-3">
                <div class="form-check">
                  <input
                    class="form-check-input"
                    type="checkbox"
                    id="floatingCheck"
                  />
                  <label class="form-check-label" for="floatingCheck">
                    Check me out
                  </label>
                </div>
              </div>
              <div>
                <button type="submit" class="btn btn-primary w-md">
                  Submit
                </button>
              </div>
            </form>
          </div>
          <!-- end card body -->
        </div>
        <!-- end card -->
      </div>
      <!-- end col -->
    </div>
    <!-- end row -->
  </Layout>
</template>
