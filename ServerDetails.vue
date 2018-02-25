<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">Please Select A Server</p>
        <p v-else>Server #{{ server.id }} selected, Status: {{ server.status }}</p>
        <hr>
        <button @click="resetStatus">Change to Normal</button>
    </div>

</template>

<script>
    import { eventBus } from '../main.js';

    export default {
        data: function() {
            return {
                server: null
            }
        },
        methods: {
           resetStatus() {
               this.server.status = "Normal";
           }
        },
        created() {
            eventBus.$on('serverSelected', (server) => {
                this.server = server;
            })
        }
    }
</script>

<style>

</style>
