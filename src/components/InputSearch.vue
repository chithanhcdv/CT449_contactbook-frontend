<script>
export default {
    props: {
        modelvalue: { type: String, default: ""},
    },

    emits: ["submit", "update:modelvalue"],
    methods: {
        updateModelValue(e) {
            this.$emit("update:modelvalue", e.target.value);
        },
        submit() {
            this.$emit("submit");
        },
    },
};
</script>

<template>
    <div class="input-group">
        <input
            type="text"
            class="form-control"
            placeholder="Nhập thông tin cần tìm"
            :value="modelvalue"
            @input="updateModelValue"
            @keyup.enter="submit"   
        />

        <div class="input-group-append">
            <button
                class="btn btn-outline-secondary"
                type="button"
                @click="submit"
            >
                <i class="fas fa-search"></i> Tìm kiếm   
            </button>
        </div>
    </div>
</template>