<template>
  <div class="row">
    <div class="col-sm-4">
      <div class="card">
        <div class="card-body">
          <button class="btn btn-primary" @click="setType('family')">
            Family
          </button>
          <p class="card-text">Family first.</p>
        </div>
      </div>
    </div>
    <div class="col-sm-4">
      <div class="card">
        <div class="card-body">
          <button class="btn btn-dark" @click="setType('friends')">
            Friends
          </button>
          <p class="card-text">That's what friends are for.</p>
        </div>
      </div>
    </div>
    <div class="col-sm-4">
      <div class="card">
        <div class="card-body">
          <button class="btn btn-danger" @click="setType('funny')">
            Funny
          </button>
          <p class="card-text">Only fun.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  emits: ["set-type"],
  setup(props, { emit }) {
    const setType = function (type) {
      emit("set-type", type);
    };

    return {
      setType,
    };
  },
};
</script>

<style>
</style>