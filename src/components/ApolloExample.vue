<template>
  <div class="apollo-example">
    <button>登录</button>
  </div>
</template>

<script>
import ApolloClient from 'apollo-boost';
import gql from 'graphql-tag';

const client = new ApolloClient({
  uri: 'http://localhost:7002/graphql'
});

client.query({
  query: gql`
    query user{
      name
    }
  `,
})
  .then(data => console.log(data))
  .catch(error => console.error(error));

export default {
  data () {
    return {
      id: 3
    }
  },

  computed: {

  },

  methods: {
    
  },
}
</script>

<style scoped>
.form,
.input,
.apollo,
.message {
  padding: 12px;
}

.input {
  font-family: inherit;
  font-size: inherit;
  border: solid 2px #ccc;
  border-radius: 3px;
}

.error {
  color: red;
}
</style>
