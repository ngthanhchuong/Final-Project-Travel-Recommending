<template>
  <section class="py-5 bg-light">
    <div class="container">
      <h2 class="mb-4">Tourists</h2>
      <div class="row">
        <div
          class="col-lg-4 col-sm-6 mb-4"
          v-for="item in posts"
          :key="item.id"
        >
          <div class="card h-100">
            <a href="#!"
              ><img class="card-img-top" :src="item.image" alt="..."
            /></a>
            <!-- <img class="img-fluid rounded" :src="post.image" alt="..." /> -->

            <div class="card-body">
              <h4 class="card-title">{{ item.header }}</h4>
              <p class="card-text">
                {{ item.description }}
              </p>
              <p id="location">{{ item.location }}</p>
              <div class="card-price" id="prices">
                <a class="btn btn-primary" :href="'/tour/' + item.id"
                  >From {{ item.price }}$</a
                >
              </div>
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
      process.env.URL_DEFAULT + '/tour?page=1&limit=9'
    )
  },
}
</script>
