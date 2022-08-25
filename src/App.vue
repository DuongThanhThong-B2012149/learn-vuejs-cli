<template>
  <teleport to="body">
    <modal
      v-if="isShowModal"
      title="This is a title"
      content="Learn VueJS step by step"
      @cancel="onToggleModal"
      theme="example"
    >
      <template v-slot:header>
        <div>
          <h1>This is the header...</h1>
        </div>
      </template>
      <label for="">Name</label>
      <input type="text" />
      <template v-slot:footer>
        <div>
          <h1>This is the footer...</h1>
          <button @click="onToggleModal">Cancel</button>
        </div>
      </template>
    </modal>
  </teleport>
  <button @click="onToggleModal">Show Modal</button>
</template>

<script>
import Modal from "./components/ModalApp.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      isShowModal: false,
    };
  },
  methods: {
    changeEvent() {
      // this.$refs.hello.onConsoleLogTesting();
      // console.log("Running here...");
      console.log(this.$refs.hello);
      console.log(this.$refs.header);
    },
    onToggleModal() {
      this.isShowModal = !this.isShowModal;
    },
  },
};
</script>

<style></style>
