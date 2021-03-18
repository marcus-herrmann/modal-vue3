<template>
  <div id="app">
    <!-- ... -->
    <button type="button" @click="openDialog">
      Open dialog
    </button>
    <a11y-dialog
        id="app-dialog"
        app-root="#app"
        dialog-root="#dialog-root"
        @dialog-ref="assignDialogRef"
    >
      <template v-slot:title>
        <span>Your dialog title</span>
      </template>
      <div>
        <p>Your content</p>
      </div>
    </a11y-dialog>
  </div>
</template>

<script>
export default {
  name: 'YourComponent',
  data: () => ({
    dialog: null
  }),

  methods: {
    openDialog() {
      if (this.dialog) {
        this.dialog.show()
      }
    },

    assignDialogRef(dialog) {
      this.dialog = dialog
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
