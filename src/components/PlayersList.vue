<template>
  <div class="row">
    <div class="col-3" v-for="player in players" :key="player.id">
      <div class="card">
        {{ player.player }}
        <button
          type="button"
          class="btn btn-danger"
          @click="deletePlayer(player)"
        >
          x
        </button>
      </div>
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