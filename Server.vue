<template>
    <li
            class="list-group-item"
            style="cursor: pointer"
            @click="serverSelected">
        Server #{{ server.id }}
    </li>
</template>

<script>
    import { eventBus } from '../main.js';

    export default {
        props: ['server'],
        methods: {
            serverSelected() {
                eventBus.$emit('serverSelected', this.server);
            }
        }
    }
</script>