<template>
  <div class="row">
    <div class="col-3" v-for="player in players" :key="player.id">
      {{ player.player }} <button @click="deletePlayer(player)">x</button>
    </div>
  </div>
</template>

<script>
export default {
  emits: ["delete-player"],
  setup(props, { emit }) {
    const deletePlayer = function (player) {
      emit("delete-player", player);
    };

    return {
      deletePlayer,
    };
  },
  props: {
    players: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style>
</style>