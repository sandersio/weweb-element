<template>
    <div class="my-element">
        <p :style="textStyle">I am a custom element 1!</p>
        <v-select :options="['Canada', 'United States']"></v-select>
        <p :style="textStyle">I am a custom element 11 !</p>
    </div>

</template>

<script>
import Vue from 'vue'
import vSelect from 'vue-select'
import 'vue-select/dist/vue-select.css';

Vue.component('v-select', vSelect)
export default {
    name: "__COMPONENT_NAME__",
    wwDefaultContent: {
        textColor: "#F23636",
    },
    props: {
        content: { type: "Object", required: true },
    },
    computed: {
        textStyle() {
            return {
                color: this.content.textColor,
            };
        },
    },
};
</script>

<style lang="scss" scoped>
.my-element {
    p {
        font-size: 18px;
    }
    .v-select {
        width: 200px;
    }
}
</style>
