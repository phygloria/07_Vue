<script setup>
</script>

<template>
    <div class="container">
        <div class="north">
            <slot name="north"></slot>
        </div>
        <div class="east">
            <slot name="east"></slot>
        </div>
        <div class="west">
            <slot name="west"></slot>
        </div>
        <div class="south">
            <slot name="south"></slot>
        </div>
    </div>
</template>

<style>
.container {
    display: grid;
    grid-template-columns: 2fr 2fr;
    grid-template-rows: 3fr 3fr;
    gap: 10px;
}

.north {
    grid-column: 2 / span 1;
    width: 200px;
    height: 200px;
    background-color: #ff9999;
}

.south {
    grid-column: 2 / span 2;
    width: 200px;
    height: 200px;
    background-color: #99ccff;
}

.east {
    grid-column: 3 / span 1;
    width: 200px;
    height: 200px;
    background-color: #99ff99;
}

.west {
    grid-column: 1 / span 1;
    width: 200px;
    height: 200px;
    background-color: #ffcc66;
}
</style>