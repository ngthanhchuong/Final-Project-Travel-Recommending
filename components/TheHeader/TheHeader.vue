<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
      <a class="navbar-brand" href="/"
        ><span>Travello</span
        ><span style="color: rgba(255, 158, 78, 1)">Go</span>
      </a>
      <button
        class="navbar-toggler navbar-toggler-right"
        type="button"
        data-toggle="collapse"
        data-target="#navbarResponsive"
        aria-controls="navbarResponsive"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarResponsive">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <a class="nav-link" href="#">Home</a>
          </li>
          <li class="nav-item"><a class="nav-link" href="#">Explore</a></li>
          <li class="nav-item"><a class="nav-link" href="#">Travel</a></li>
          <li class="nav-item">
            <a class="nav-link" href="#">About</a>
          </li>
          <a> <b-button href="/login">SignIn</b-button> </a>

          <a><b-button @click="createPost()">Create</b-button></a>
          <!-- <a class="nav-link" href="blog-post.html">Blog</a> -->
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'TheHeader',
  data() {
    return {
      formAddTour: {
        name_tour: '',
        location: '',
        thumbnail: null,
        service_tour: [],
        description: '',
        gallery_image: [],
        location_city_id: null,
        capacity: null,
        price: null,
        discount: null,
        timing: null,
        // tourGuide_id: null
      },

      optionsCity: [],
    }
  },
  methods: {
    async createPost() {
      console.log(this.formAddTour)
      // var newData = {
      //   id: '555',
      //   header: 'Hello Number',
      //   content: 'This is number',
      //   author: 'Thanh Chuong.',
      //   date: 1620384258,
      //   image:
      //     'https://images.unsplash.com/photo-1470770841072-f978cf4d019e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1350&q=80',
      // }
      // await this.$axios.$post(process.env.URL_DEFAULT + '/Blog', newData)
    },
  },
}
</script>
