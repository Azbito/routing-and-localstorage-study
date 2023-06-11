<template>
  <div>
    <p>Hello! Let's make your ID</p>
    <div>
    <IDCard :name="name" />
    </div>
    <input @change="onChange" :value="name" />
  </div>
</template>

<script>
import { ref } from 'vue'
import IDCard from '../components/IDCard.vue' // Import the IDCard component

export default {
  name: "HomeComponent",
  components: {
    IDCard,
  },
  data() {
    const previousName = localStorage.getItem('name') || ''
    const name = ref(previousName)

    const step = 0
    return {
      name: name,
      step: step
    }
  },
  methods: {
    onChange(event) {
      this.name = event.target.value
      localStorage.setItem('name', this.name)
    }
  }
}
</script>
