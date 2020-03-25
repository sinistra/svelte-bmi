<script>
  import Bmi from "./Bmi.svelte";
  import Bmr from "./Bmr.svelte";

  let weight;
  let height;
  let age;
  let gender = "m";

  function submitBMI() {
    // console.log(event);
    console.log(weight, height, age, gender);
  }
</script>

<section>
  <div class="container">
    <div class="row mt-5">
      <h2>Body Mass Index</h2>
    </div>
    <div class="row mt-5">
      <div class="col-md-6">
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
                  placeholder="weight (in kilos)"
                  bind:value={weight} />
              </div>
              <div class="form-group">
                <label for="height">Height</label>
                <input
                  type="text"
                  class="form-control"
                  id="height"
                  placeholder="height (in cm)"
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
              <br />
              <br />
              <button
                type="submit"
                on:click|preventDefault={submitBMI}
                class="btn btn-primary">
                Calculate
              </button>
            </form>
          </div>
        </div>
      </div>
      <div class="col-md-6">
        <div class="card">
          <div class="card-header">Results</div>
          <div class="card-body">
            <Bmi {weight} {height} />
            <Bmr {weight} {height} {age} {gender} />
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
