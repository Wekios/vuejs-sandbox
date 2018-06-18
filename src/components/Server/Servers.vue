<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <li
            class="list-group-item"
            v-for="(server,index) in servers" :key="index.id">
            Server #{{ index }} {{ server.status }}</li>
            <button @click="updateServer" class="btn btn-primary btn-lg btn-block"> Update server </button>
        </ul>
    </div>
</template>

<script>
export default {
  data() {
    return {
      servers: [
        { id: 1, status: "Normal" },
        { id: 1, status: "Critical" },
        { id: 1, status: "Unknown" },
        { id: 1, status: "Normal" }
      ]
    };
  },
  methods: {
    updateServer() {
      this.$emit("serversUpdated", this.server.status);
    }
  }
};
</script>

<style scoped>
</style>