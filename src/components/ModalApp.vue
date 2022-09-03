<template>
  <div id="myModal" class="modal" @click.self="onHideModal">
    <div class="header">
      <slot name="header" />
    </div>

    <!-- Modal content -->
    <div class="modal-content" :class="{ themeActive: theme === 'example' }">
      <span class="close">&times;</span>
      <slot />
      <!-- <p>{{ content }}</p> -->
    </div>
    <div class="">
      <slot name="footer" />
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalApp",
  props: {
    title: {
      type: String,
      required: true,
    },
    content: {
      type: String,
      default: "",
    },
    theme: {
      type: String,
      required: true,
      default: "example",
      validator(val) {
        return ["example", "temp"].includes(val);
      },
    },
  },
  data() {
    return {};
  },
  methods: {
    onHideModal() {
      console.log(123);
      this.$emit("cancel");
    },
  },
};
</script>

<style scoped>
/* The Modal (background) */
.modal {
  display: block; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  padding-top: 100px; /* Location of the box */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0, 0, 0); /* Fallback color */
  background-color: rgba(0, 0, 0, 0.4); /* Black w/ opacity */
}

/* Modal Content */
.modal-content {
  background-color: #fefefe;
  margin: auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}

/* The Close Button */
.close {
  color: #aaaaaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
}
.themeActive {
  background: palegreen;
}
</style>
