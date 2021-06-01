<template>
  <section class="py-5">
    <div class="container">
      <!-- Page Heading/Breadcrumbs-->
      <h1 class="mt-4 mb-3">{{ post.header }}</h1>
      <div class="row">
        <!-- Post Content Column-->
        <div class="col-lg-8">
          <!-- Preview Image-->
          <img class="img-fluid rounded" :src="post.image" alt="..." />
          <hr />
          <!-- Date/Time-->
          <p>Date: {{ formatDate(post.date) }}</p>
          <p>Author: {{ post.author }}</p>

          <hr />
          <!-- Post Content-->
          <p>{{ post.content }}</p>
          <hr />
        </div>
        <br />
        <!-- <div class="mb-6"> -->
        <!-- Embedded Google Map-->
        <!-- <iframe
            style="width: 100%; height: 400px; border: 0"
            src="http://maps.google.com/maps?hl=en&amp;ie=UTF8&amp;ll=37.0625,-95.677068&amp;spn=56.506174,79.013672&amp;t=m&amp;z=4&amp;output=embed"
          ></iframe>
        </div> -->
      </div>
    </div>
  </section>
</template>

<script>
import { formatDate } from '@/plugins/define-function'
export default {
  async asyncData({ params, $axios }) {
    // const post = await $axios.$get(
    //   `https://5f8e9be3693e730016d7a478.mockapi.io/tour/${params.id}`
    // );
    const post = await $axios.$get(
      process.env.URL_DEFAULT + '/Blog/' + params.id
    )
    const getIDPost = post.id
    // const getTourGuideIPost = post.tourGuide_id._id;
    // const value_rating = post.raking
    // const value_total_rating = post.total_rating
    return {
      post,
      getIDPost,
      //   getTourGuideIDPost,
      //   value_rating ,
      //   value_total_rating
    }
  },
}
</script>
