<template>
  <div>
    <h2 class="mb-3 primary--text headline">Edit Profile</h2>
    <profile-edit-form @success="success"></profile-edit-form>
  </div>
</template>

<script>
  export default {
    components: {
      'profile-edit-form': require('./ProfileEditForm')
    },

    methods: {
      success(data) {
        this.$store.dispatch('auth/setUser', data)
        this.$router.push({ name: 'profile' })
      }
    }
  }
</script>
