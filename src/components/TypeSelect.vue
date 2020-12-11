<template>
  <div class="row">
    <div class="col-sm-4">
      <div class="card">
        <div class="card-body">
          <h5 class="card-title">Family</h5>
          <p class="card-text">Family first.</p>
          <a href="#" class="btn btn-primary">Go</a>
        </div>
      </div>
    </div>
    <div class="col-sm-4">
      <div class="card">
        <div class="card-body">
          <h5 class="card-title">Friends</h5>
          <p class="card-text">That's what friends are for.</p>
          <a href="#" class="btn btn-dark">Go</a>
        </div>
      </div>
    </div>
    <div class="col-sm-4">
      <div class="card">
        <div class="card-body">
          <h5 class="card-title">Extrême</h5>
          <p class="card-text">Adults only.</p>
          <a href="#" class="btn btn-danger">Go</a>
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