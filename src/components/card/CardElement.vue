<script setup>

const props = defineProps(['items'])

// const handleModalOpen = (event) => {
//     return console.log(props, event)
// };

</script>

<template>
<ul class="posts">
    <li v-for="item in props.items" :key="item.id_string">
        <a :href="item.post_url" target="_blank">
            <div v-html="item.body"></div>
        </a>
    </li>
</ul>
</template>

<style lang="scss">
.posts {
    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    justify-content: flex-start;
    margin: 0;
    padding: 0;
    list-style: none;

    li {
        position: relative;
        display: flex;
        flex: 0 0 50%;
        max-width: 50%;
        overflow: hidden;
        height: 200px;
    }

    img {
        object-fit: cover;
        height: 100%;
        position: absolute;
        left: 0;
        top: 0;
    }
}

@media (min-width: 768px) {
    .posts li {
        flex: 0 0 25%;
        max-width: 25%;
    }
}

@media (min-width: 1200px) {
    .posts li {
        flex: 0 0 12.5%;
        max-width: 12.5%;
    }
}
</style>

