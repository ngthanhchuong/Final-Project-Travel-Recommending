<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label="Email address:"
        label-for="input-1"
        description="We'll never share your email with anyone else."
      >
        <b-form-input
          id="input-1"
          v-model="form.email"
          type="email"
          placeholder="Enter email"
          required
        ></b-form-input>
      </b-form-group>

      <!-- Placeholder - Input -->
      <b-form-group id="input-group-2" label="Your Title:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.title"
          placeholder="Enter title"
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-3" label="image:" label-for="input-3">
        <b-form-select
          id="input-3"
          v-model="form.image"
          placeholder="Enter URL:"
          required
        ></b-form-select>
      </b-form-group>

      <b-form-group
        id="input-group-4"
        label="Your Description:"
        label-for="input-4"
      >
        <b-form-input
          id="input-4"
          v-model="form.description"
          placeholder="Description"
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-5" label="Location:" label-for="input-5">
        <b-form-input
          id="input-5"
          v-model="form.location"
          placeholder="Location"
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-6" label="Price" label-for="input-6">
        <b-form-input
          id="input-6"
          v-model="form.price"
          placeholder="Price"
          required
        ></b-form-input>
      </b-form-group>

      <!-- <b-form-group id="input-group-4" v-slot="{ ariaDescribedby }">
        <b-form-checkbox-group
          v-model="form.checked"
          id="checkboxes-4"
          :aria-describedby="ariaDescribedby"
        >
          <b-form-checkbox value="me">Check me out</b-form-checkbox>
          <b-form-checkbox value="that">Check that out</b-form-checkbox>
        </b-form-checkbox-group>
      </b-form-group> -->

      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
    <b-card class="mt-3" header="Form Data Result">
      <pre class="m-0">{{ form }}</pre>
    </b-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: '',
        name: '',
        food: null,
        checked: [],
      },
      foods: [
        { text: 'Select One', value: null },
        'Carrots',
        'Beans',
        'Tomatoes',
        'Corn',
      ],
      show: true,
    }
  },
  methods: {
    onSubmit(event) {
      event.preventDefault()
      alert(JSON.stringify(this.form))
    },
    onReset(event) {
      event.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.name = ''
      this.form.food = null
      this.form.checked = []
      // Trick to reset/clear native browser form validation state
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    },
  },
}
</script>
