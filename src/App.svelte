<script>

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
        <div class="card p-2 shadow">
          <div class="card-body">
            <h5 class="card-title mb-4">Add New Note</h5>
            <form>
              <div class="form-group">
                <label for="title">Title</label>
                <input
                  type="text"
                  class="form-control"
                  id="text"
                  placeholder="Note Title" />
              </div>
              <div class="form-group">
                <label for="category">Category</label>
                <select class="form-control" id="category">
                  <option selected disaabled>Selecet a category</option>
                  <option>School</option>
                  <option>School</option>
                  <option>School</option>
                </select>
              </div>
              <div class="form-group">
                <label for="content">Content</label>
                <textarea
                  class="form-control"
                  id="content"
                  rows="3"
                  placeholder="Note Content" />
              </div>
              <button
                type="submit"
                on:click|preventDefault={addNote}
                class="btn btn-primary">
                Add Note
              </button>
            </form>
          </div>
        </div>
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
