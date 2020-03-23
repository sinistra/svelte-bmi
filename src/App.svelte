<script>
  import Details from "./components/Details.svelte";
</script>

<style>
  @import url("https://fonts.googleapis.com/css?family=Nunito&display=swap");
  * {
    font-family: "Nunito", sans-serif;
  }
</style>

<section>
  <div class="container">
    <div class="row mt-5">
      <div class="col-md-6">
        <Details />
      </div>
      <div class="col-md-6">
        <div class="card">
          <div class="card-header">Category</div>
          <div class="card-body">
            <h5 class="card-title">Title of Note</h5>
            <p class="card-text">Some description of this note</p>
            <button class="btn btn-info">Edit</button>
            <button class="btn btn-danger">Delete</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
