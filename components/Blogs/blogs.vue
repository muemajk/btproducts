<style>
.blogcard h1 {
  color: white;
  position: absolute;
  bottom: 50px;
  left: 0;
  text-shadow: 2px 2px #4a494968;
}
.readbtn {
  background-color: var(--primary-color);
  border: 1px solid var(--secondary-color);
}
</style>
<template>
  <div
    class="blogcard bg-white h-64 relative rounded-lg overflow-hidden flex shadow-xl"
  >
    <img class="flex-initial" :src="blog.img" alt="No image" />
    <div class="p-3 h-full">
      <h1 class="font-bold">{{ blog.title }}</h1>
      <p class="text-left">{{ blog.short_description }}</p>
      <p class="text-left italic">{{ blog.author }}</p>
      <div class="absolute bottom-0 right-0">
        <button
          class="readbtn m-2 float-right text-white font-bold py-2 px-4 rounded"
        >
          Read
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    blog: {
      type: Object,
      default: null,
    },
  },
}
</script>
