<template>
    <div class="element">
        <div class="preview" @click="showDescription=!showDescription">
            <div class="name">{{ name }}</div>
            <div
            @mouseover="showTrash=true"
            @mouseleave="showTrash=false"
            class="work-process--delete" 
            @click="$emit('deleteElement', id)">
                <i v-if="showTrash" class="fa-solid fa-trash fa-2xs"></i>
                <i v-else class="fa-solid fa-circle fa-2xs"></i>
            </div>
        </div>
        <description-component v-if="showDescription"
        :showDescription="showDescription"
        :description="description"
        @close-desc="(closeDescription) => showDescription=closeDescription"
        ></description-component>
    </div>
</template>

<script>
import DescriptionComponent from './descriptionComponent.vue';

export default {
    name: "ListComponent",
    props: ["id", "name", "description"],
    components: { DescriptionComponent },
    data() {
        return {
            showTrash: false,
            showDescription: false
        };
    }
}
</script>


<style>
.preview {
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    transition: 0.2s;
    border-radius: 13px;
    padding-left: 10px;
    padding-right: 10px;
}

.preview:hover {
    background-color: rgb(224, 238, 247);
}

.work-process--delete {
    position: relative;
    min-height: 32px;
    min-width: 32px;
    z-index: 100;

    color: rgb(194, 94, 94);
}

.work-process--delete:hover {
    color: rgb(211, 0, 0);
}
</style>