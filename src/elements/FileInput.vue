<template>
    <input
        @input="onInput"
        v-model="inputValue"
        class="shadow appearance-none border rounded w-full py-2 px-3 bg-grey-lighter text-grey-darker leading-tight focus:outline-none focus:shadow-outline"
        :id="id"
        type="email"
        :placeholder="placeholder">
</template>

<style>


</style>

<script>

export default {
    data() {
        return {
            inputValue: '',
        }
    },
    watch: {
        value: {
            handler(newVal) {
                this.inputValue = newVal;
            }
        }
    },
    props: {
        value: {
            type: String,
            default: '',
        },
        placeholder: {
            type: String,
            default: '',
        },
        id: {
            type: String,
            default: '',
        },
    },
    methods: {
        onInput(event) {
            let value = event.srcElement.value;

            this.$emit("input", value);
        }
    },
    created: function() {
        this.inputValue = this.value;
    }
}

</script>
