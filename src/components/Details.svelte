<script>
  let weight;
  let height;
  let age;
  let gender = "m";

  function submitBMI() {
    console.log(event);
    console.log(weight, height, age, gender);
  }
</script>

<div class="card p-2 shadow">
  <div class="card-body">
    <h5 class="card-title mb-4">Your details</h5>
    <form>
      <div class="form-group">
        <label for="weight">Weight</label>
        <input
          type="text"
          class="form-control"
          id="weight"
          placeholder="weight"
          bind:value={weight} />
      </div>
      <div class="form-group">
        <label for="height">Height</label>
        <input
          type="text"
          class="form-control"
          id="height"
          placeholder="height"
          bind:value={height} />
      </div>
      <div class="form-group">
        <label for="age">Age</label>
        <input
          type="text"
          class="form-control"
          id="age"
          placeholder="age"
          bind:value={age} />
      </div>
      <div class="form-check form-check-inline">
        <input
          class="form-check-input"
          type="radio"
          name="gender"
          id="male"
          value="m"
          bind:group={gender} />
        <label class="form-check-label" for="male">Male</label>
      </div>
      <div class="form-check form-check-inline">
        <input
          class="form-check-input"
          type="radio"
          name="gender"
          id="female"
          value="f"
          bind:group={gender} />
        <label class="form-check-label" for="female">Female</label>
      </div>
      <div />
      <button
        type="submit"
        on:click|preventDefault={submitBMI}
        class="btn btn-primary">
        Add Note
      </button>
    </form>
  </div>
</div>
