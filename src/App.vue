<template>
  <div class="">
    <teleport to="body">
      <modal-app
        v-if="isShowModal"
        title="This is a title"
        content="Learn VueJS step by step"
        @cancel="onToggleModal"
        ref="hello"
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
    <h1 ref="hello">123</h1>
    <p v-for="(item, index) in lists" :key="index" :ref="`${item}`">
      {{ item }}
    </p>
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
      lists: [1, 2, 3],
    };
  },
  methods: {
    changeEvent() {
      // this.$refs.hello.onConsoleLogTesting();
      // console.log("Running here...");
      console.log(this.$refs.hello);
      // console.log(this.$refs.header);
    },
    onToggleModal() {
      console.log("onToggleModal");
      this.isShowModal = !this.isShowModal;

      console.log(this.$refs);
    },
  },
};
</script>

<style></style>
