<template>
<div class="description">
    {{ description }}
    <div class="close" @click="$emit('closeDesc', !showDescription)">
        <i class="fa-solid fa-chevron-up close__chevron"></i>
    </div>
</div>
</template>

<script>
export default {
    name: 'DescriptionComponent',
    props: ['showDescription', 'description']
}
</script>

<style>
.description {
    display: flex;
    justify-content: space-between;
    gap: 8px;

    margin: 10px 17px 10px 30px;
    font-size: 25px;
}

.close {
    min-width: 25px;
    position:relative;
    color: rgb(113, 113, 113);
}

.close__chevron {
    cursor: pointer;

    position: absolute;
    bottom: 0;
    padding: 4px;

    border-radius: 50%;
}

.close__chevron:hover {
    background-color: rgb(224, 238, 247);
}
</style>