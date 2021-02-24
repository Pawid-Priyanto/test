<template>
    <fieldset :id="id">
        <div v-for="(option, idx) in options" :key="option.text">
            <input
                :id="id+ idx"
                :name="id"
                type="radio"
                :value="options.value"
                @change="changeValue(option.value)"
            />
            <label :for="id + idx">{{option.text}}</label>
            <slot v-if="option.value === value" :name="option.value"></slot>
        </div>
    </fieldset>
</template>

<script>
export default {
     model: {
        event: 'change',
    },
    props: {
        id: {
            type: String,
            required: true,
        },
        value: {
            type: [String, Number, Boolean, Object],
            default: null
        },
        options: {
            type: [Array],
            required: true
        }
    },
    methods: {
        changeValue(value){
            this.$emit('change', value)
        }
    }
}
</script>