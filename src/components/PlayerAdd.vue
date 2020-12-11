<template>
  <div class="row">
    <div v-if="showAlert" class="alert alert-danger" role="alert">
      You must specify a player name !
    </div>
  </div>
  <div class="row justify-content-center">
    <div class="col-4">
      <input
        type="text"
        name="player"
        placeholder="Player's name"
        v-model="playerToAdd"
        @keypress.enter="addPlayer"
      />
    </div>
    <div class="col-4">
      <button type="button" class="btn btn-success" @click="addPlayer">
        Add player
      </button>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  emits: ["add-player"],
  setup(props, { emit }) {
    let playerToAdd = ref("");
    let showAlert = ref(false);

    const addPlayer = function () {
      if (playerToAdd.value) {
        emit("add-player", playerToAdd.value);
        playerToAdd.value = "";
        showAlert.value = false;
      } else {
        showAlert.value = true;
      }
    };

    return {
      playerToAdd,
      addPlayer,
      showAlert,
    };
  },
};
</script>

<style>
</style>