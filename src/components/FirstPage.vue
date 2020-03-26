<template>
  <v-container>
    <v-row>
      <v-col>
        {{title}}
      </v-col>
    </v-row>
    <v-flex sm12 lg12 mb-3 pl-0 pr-4>
      <v-simple-table>
        <template v-slot:default>
          <thead>
          <tr>
            <th class="text-left">Name</th>
            <th class="text-left">Role</th>
          </tr>
          </thead>
          <tbody>
          <tr v-for="(player, index) in players" :key="index"  style="height: 75px">
            <td>{{ player.name }}</td>
            <td>{{ player.role }}</td>
          </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-flex>
  </v-container>
</template>

<script>
  export default {
    name: 'FirstPage',

    data: () => ({
      title: 'Players'
    }),
    computed: {
      players(){
        return this.$store.state.players
      }
    },
    created() {
      this.$store.dispatch('retrievePlayers');
    }
  }
</script>

<style scoped>

</style>
