<template>
  <div className="home-container">
    <div>
      <IDCard :name="infosParsed.name" :lastName="infosParsed.lastName" :nickname="infosParsed.nickname"/>
    </div>
    <div class="container-info-changer">
       <input placeholder="What's your first name?" @input="onChange('name', $event.target.value)" :value="infos.name" />
       <input placeholder="What's your last name?" @input="onChange('lastName', $event.target.value)" :value="infos.lastName" />
       <input placeholder="What's your nickname?" @input="onChange('nickname', $event.target.value)" :value="infos.nickname" />
       <button @click="saveData()">Save</button>
    </div>
  </div>
</template>

<style lang="scss">
.home-container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  margin-top: 4rem;
  gap: 4rem;
}
.container-info-changer {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  background-color: rgb(54, 54, 54);
  width: 40%;
  padding: 2rem 0;
  gap: 1rem;
  border-radius: 16px;

  input {
    border: none;
    outline: none;
    padding: .5rem;
    border-radius: 16px
  }

  button {
    border: none;
    outline: none;
    padding: .5rem;
    border-radius: 16px;
    background-color: rgb(40, 184, 27);
    color: white;
    cursor: pointer;
    transition: .2s;

    &:hover {
      background-color: rgb(37, 156, 26);
    }

    &:active {
      background-color: rgb(31, 126, 23);
    }
  }
}
</style>

<script>
import IDCard from '../components/IDCard.vue'

export default {
  name: "HomeComponent",
  components: {
    IDCard,
  },
  data() {
    return {
      infos: {
        name: '',
        lastName: '',
        nickname: ''
      },
      infosParsed: {}
    }
  },
  mounted() {
    const storedInfos = localStorage.getItem('infos')
    if (storedInfos) {
      this.infosParsed = JSON.parse(storedInfos)
    }
  },
  methods: {
    onChange(prop, value) {
      this.infos[prop] = value
    },
    saveData() {
      if (this.infos.name && this.infos.lastName && this.infos.nickname !== '') {
        localStorage.setItem('infos', JSON.stringify(this.infos))
        location.reload()
        return;
      }
      alert('Please, fill all the blanks')
    }
  }
}
</script>

