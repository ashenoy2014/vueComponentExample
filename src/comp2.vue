<template>
    <div id="comp2">
        <input v-model="inmsg"
                type="text">
        <h2 class="msg">
            {{inmsg + " Avi"}}
        </h2>
    </div>
</template>

<script>
export default {
    data() {
        return {
            inmsg: "component 2 message"

        };
    },
};
</script>

<style>
.msg {
    font-size: 25px;
    font-family: 'Roboto', sans-serif;
    color: blue;
}
</style>