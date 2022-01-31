<script>
import CKEditor from "@ckeditor/ckeditor5-vue";
import ClassicEditor from "@ckeditor/ckeditor5-build-classic";

/**
 * Side-panel component
 */
export default {
  components: {
    ckeditor: CKEditor.component,
  },
  data() {
    return {
      showModal: false,
      editor: ClassicEditor,
      editorData: "<p>Content of the editor.</p>",
    };
  },
};
</script>

<template>
  <div class="inbox-leftbar">
    <div class="d-grid">
      <b-button block variant="danger" @click="showModal = true"
        >Compose</b-button
      >
    </div>
    <div class="mail-list mt-4">
      <router-link tag="a" to="/email/inbox" class="text-danger">
        <i class="ri-inbox-fill align-bottom me-2"></i>Inbox
        <span class="badge badge-soft-danger float-end ms-2">7</span>
      </router-link>

      <router-link tag="a" to="/email/inbox">
        <i class="ri-star-line align-bottom me-2"></i>Starred
      </router-link>
      <a href="javascript: void(0);"
        ><i class="ri-time-line align-bottom me-2"></i>Snoozed</a
      >
      <a href="javascript: void(0);"
        ><i class="ri-file-list-2-line align-bottom me-2"></i>Draft<span
          class="badge badge-soft-info float-end ms-2"
          >32</span
        ></a
      >
      <a href="javascript: void(0);"
        ><i class="ri-send-plane-2-line align-bottom me-2"></i>Sent Mail</a
      >
      <a href="javascript: void(0);"
        ><i class="ri-delete-bin-line align-bottom me-2"></i>Trash</a
      >
      <a href="javascript: void(0);"
        ><i class="ri-price-tag-3-line align-bottom me-2"></i>Important</a
      >
      <a href="javascript: void(0);"
        ><i class="ri-error-warning-line align-bottom me-2"></i>Spam</a
      >
    </div>

    <h6 class="mt-4">Labels</h6>

    <div class="list-group b-0 mail-list">
      <a href="#" class="list-group-item border-0"
        ><span class="mdi mdi-circle text-info me-2"></span>Web App</a
      >
      <a href="#" class="list-group-item border-0"
        ><span class="mdi mdi-circle text-warning me-2"></span>Recharge</a
      >
      <a href="#" class="list-group-item border-0"
        ><span class="mdi mdi-circle text-dark me-2"></span>Wallet Balance</a
      >
      <a href="#" class="list-group-item border-0"
        ><span class="mdi mdi-circle text-primary me-2"></span>Friends</a
      >
      <a href="#" class="list-group-item border-0"
        ><span class="mdi mdi-circle text-success me-2"></span>Family</a
      >
    </div>

    <b-modal v-model="showModal" title="New Message" centered>
      <form>
        <div class="mb-2">
          <label for="messageto-input" class="form-label">To</label>
          <input
            type="email"
            class="form-control"
            id="messageto-input"
            placeholder="Example@email.com"
          />
        </div>

        <div class="mb-2">
          <label for="subject-input" class="form-label">Subject</label>
          <input
            type="text"
            class="form-control"
            id="subject-input"
            placeholder="Your subject"
          />
        </div>
        <div class="mb-2">
            <label for="subject-input" class="form-label">Message</label>
          <ckeditor v-model="editorData" :editor="editor"></ckeditor>
        </div>
      </form>
      <template v-slot:modal-footer>
        <b-button variant="secondary" @click="showModal = false"
          >Close</b-button
        >
        <b-button variant="primary">
          Send
          <i class="fab fa-telegram-plane ms-1"></i>
        </b-button>
      </template>
    </b-modal>
  </div>
</template>
