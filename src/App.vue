<template>
  <div class="container">
    <h1>Truth <small class="text-muted">or dare ?</small></h1>
    <figcaption class="blockquote-footer">
      You have never enjoyed this game
      <cite title="Source Title">so much.</cite>
    </figcaption>
    <hr />
    <PlayerAdd @add-player="savePlayer" />
    <TypeSelect @set-type="saveType" />
    <PlayersList :players="players" @delete-player="deletePlayer" />
    <button
      type="button"
      class="btn btn-success"
      :class="{ disabled: notReady }"
      @click="startGame()"
    >
      Commencer la partie
    </button>
  </div>
</template>

<script>
import PlayerAdd from "@/components/PlayerAdd";
import PlayersList from "@/components/PlayersList";
import TypeSelect from "@/components/TypeSelect";

import { ref } from "vue";

export default {
  name: "App",
  components: {
    PlayerAdd,
    PlayersList,
    TypeSelect,
  },
  setup() {
    let players = ref([]);
    let gameType = ref("");
    let notReady = ref(true);

    const savePlayer = function (data) {
      players.value = [...players.value, { player: data, id: Date.now() }];
    };

    const deletePlayer = function (data) {
      players.value = players.value.filter((p) => p.id !== data.id);
    };

    const saveType = function (data) {
      gameType = data;
    };

    const startGame = function () {
      console.log("Players :", players.value);
      console.log("Game type :", gameType);
    };

    return {
      savePlayer,
      saveType,
      deletePlayer,
      players,
      gameType,
      startGame,
      notReady,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
