<template>
  <div class="container">
    <div class="names">
      <div class="info">
      <strong>Name: <b>{{ name }}</b></strong>
      </div>
      <div class="info">
      <strong>Last Name: <b>{{ lastName }}</b></strong>
      </div>
      <div class="info">
      <strong>Nickname: <b>{{ nickname }}</b></strong>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "IDCard",
  props: {
    name: String,
    lastName: String,
    nickname: String
  },
}
</script>

<style lang="scss">
.container {
  background-color: rgb(73, 73, 73);
  border-radius: 15px 0px 15px 0px;
  width: 30rem;
  padding: 1rem;
  display: flex;
  flex-direction: column;

.names {
  padding: 1rem;
  border-radius: 16px;
  background-color: rgba(0, 0, 0, 0.37);
  
  strong {
    b {
      font-weight: 400;
    }
  }
}
}
</style>


