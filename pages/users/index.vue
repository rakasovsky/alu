<template>
    <section>
        <h1>{{pageTitle}}</h1>
          <ul>
              <li v-for="user of users" :key='user.id'>
                <a href="#" @click.prevent='openUser(user)'>{{user.name}} </a>
              </li>
          </ul>
    </section>
</template>

<script>
export default {

    //для статичной отрисовки страницы на стороне сервера
    async fetch({store}) {
        if (store.getters['users/users'].length === 0) {
            await store.dispatch('users/fetch')
        }
    },
    //Получение юзеров с сервера
    data: () => ({
       pageTitle: 'Users page'
    }),
    computed: {
        users() {
            return this.$store.getters['users/users']
        }
    },
    methods: {
        openUser(user) {
            this.$router.push('/users/' + user.id)
            
        }
    }
}
</script>