<template>
  <section class="py-5">
    <div class="container">
      <h1 class="mb-4">Welcome to Blog</h1>
      <!-- Marketing Icons Section-->
      <div class="row">
        <div
          class="col-md-4 col-lg-4 col-sm-6 mb-4"
          v-for="item in posts"
          :key="item.id"
        >
          <div class="card h-100">
            <h4 class="card-header">{{ item.header }}</h4>
            <div class="card-body">
              <p class="card-text">{{ item.description }} .........</p>
            </div>
            <div class="card-footer">
              <a class="btn btn-primary" :href="'/blog/' + item.id"
                >Read More</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      posts: [],
    }
  },
  async fetch() {
    this.posts = await this.$axios.$get(
      process.env.URL_DEFAULT + '/Blog?page=1&limit=6'
    )
  },
}
</script>
