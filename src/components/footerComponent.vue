<template>
    <footer class="menu">
            <div class="add">
                <i class="fa-solid fa-plus fa-xs"></i>
            </div>
        </footer>
</template>

<script>
export default {
    name: 'FooterComponent'
}
</script>

<style>
footer {
    cursor: pointer;
    position: fixed;
    background-color: rgb(66, 194, 66);
    width: 100%;
    height: 70px;
    bottom: 0;
    color: white;

    display: flex;
    align-items: center;
    justify-content: center;
}

footer:hover {
    background-color: rgb(33, 212, 33);
}

.add {
    font-size: 50px;
}
</style>