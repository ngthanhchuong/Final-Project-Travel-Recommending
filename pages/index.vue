<template>
  <div>
    <Slide />
    <Blog />
    <Tourist />
  </div>
</template>

<script>
// import PopularPost from '@/components/PopularPost/PopularPost.vue'
// import Offers from '@/components/Offers/Offers.vue'
// import OurBlogs from '@/components/OurBlogs/OurBlogs.vue'
import Slide from '@/components/Slide/Slide.vue'
import Blog from '@/components/Blog/Blog.vue'
import Tourist from '@/components/Tourist/Tourist.vue'

export default {
  components: {
    Slide,
    Blog,
    Tourist,
    // PopularPost,
    // Offers,
    // OurBlogs,
  },
}
</script>
