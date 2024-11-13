<script setup>
import { ref, onMounted } from 'vue';
const meta = import.meta.env;
const apiKey = meta.VITE_TUMBLR_API_KEY;
const apiURL = meta.VITE_TUMBLR_API;
const blogURL = meta.VITE_TUMBLR_BLOG_URL;

import CardElement from '../components/card/CardElement.vue';

let postItems = ref([]);

const options = {
    method: 'GET',
    headers: {
        'Content-Type': 'application/json'
    }
};

const url = new URL(`https://${apiURL}${blogURL}/posts?limit=50`);
url.searchParams.set('api_key', apiKey );

onMounted(() => {
  fetch(url, options)
    .then((response) => response.json())
    .then((response) => {
      if (response.meta.status === 200) {
        postItems.value = response.response.posts;
        return postItems;
      }
    })
    .catch(err => console.log(err));
});
</script>

<template>
  <main>
    <div class="home">
      <p>This is the home page</p>
      <CardElement :items="postItems" v-if="postItems.length"/>
      <div v-else>
        No posts to display  
      </div>
  </div>

  </main>
</template>
