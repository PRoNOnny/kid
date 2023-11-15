<template>
    <BForm @submit="onSubmit" @reset="onReset" v-if="show">
      <BFormGroup
        id="input-group-1"
        label="Email address:"
        label-for="input-1"
        description="We'll never share your email with anyone else." 
      >
        <BFormInput
          id="input-1"
          v-model="form.email"
          type="email"
          placeholder="Enter email"
          required
        />
      </BFormGroup>
  
      <BFormGroup id="input-group-2" label="Your Name:" label-for="input-2">
        <BFormInput id="input-2" v-model="form.name" placeholder="Enter name" required />
      </BFormGroup>
      <BFormGroup id="input-group-3" label="Branch:" label-for="input-3">
        <BFormSelect id="input-3" v-model="form.Branch" :options="Branch" required />
      </BFormGroup>
  
      <BFormGroup id="input-group-4">
        <BFormCheckboxGroup v-model="form.checked" id="checkboxes-4">
          <BFormCheckbox value="Rating 1">1 STAR</BFormCheckbox>
          <BFormCheckbox value="Rating 2">2 STAR</BFormCheckbox>
          <BFormCheckbox value="Rating 3">3 STAR</BFormCheckbox>
          <BFormCheckbox value="Rating 4">4 STAR</BFormCheckbox>
          <BFormCheckbox value="Rating 5">5 STAR</BFormCheckbox>
        </BFormCheckboxGroup>
      </BFormGroup>
      <BButton type="submit" variant="primary">Submit</BButton>
      <BButton type="reset" variant="danger">Reset</BButton>
    </BForm>
  
    <!-- <BCard class="mt-3" header="Form Data Result">
      <pre class="m-0">{{ form }}</pre>
    </BCard> -->
  </template>
  <style>
  .form{
    margin: 0 10rem;
  }

  .form-text{
    font-size: 12px !important;
  }

</style>
  <script setup lang="ts">
  import {reactive , ref , nextTick} from 'vue'
  const Branch = [{text: 'Select One', value: null}, 'Siam Paragon', 'Central Festival', 'Icon Siam']
  
  const form = reactive({
    email: '',
    name: '',
    Branch: null,
    checked: [],
  })
  const show = ref(true)
  
  const onSubmit = (event) => {
    event.preventDefault()
    alert(JSON.stringify(form))
  }
  
  const onReset = (event) => {
    event.preventDefault()
    // Reset our form values
    form.email = ''
    form.name = ''
    form.Branch = null
    form.checked = []
    // Trick to reset/clear native browser form validation state
    show.value = false
    nextTick(() => {
      show.value = true
    })
  }
  </script>