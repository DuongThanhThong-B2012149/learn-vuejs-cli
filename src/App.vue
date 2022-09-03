<template>
  <div class="">
    <teleport to="body">
      <modal-app
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
      </modal-app>
    </teleport>
    <button @click="onToggleModal">Show Modal</button>
  </div>
</template>

<script>
import ModalApp from "./components/ModalApp.vue";
export default {
  components: { ModalApp },
  name: "App",

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
      console.log("onToggleModal");
      this.isShowModal = !this.isShowModal;
    },
  },
};
</script>

<style></style>
