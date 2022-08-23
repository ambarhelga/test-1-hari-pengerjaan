//Register.vue
<template>
  <div class="container">
    <div class="row justify-content-md-center">
      <div class="col-md-4">
        <div class="card">
          <div class="card-header">Tambah Buku</div>
          <div class="card-body">
            <form>
              <div class="form-group">
                <label for="name">Judul</label>
                <input
                  type="string"
                  class="form-control"
                  placeholder="Judul buku"
                  v-model="Judul"
                />
              </div>
              <div class="form-group">
                <label for="isbn">ISBN</label>
                <input
                  type="string"
                  class="form-control"
                  placeholder="no ISBN"
                  v-model="isbn"
                />
              </div>
              <div class="form-group">
                <label for="author">Penerbit</label>
                <input
                  type="text"
                  class="form-control"
                  placeholder="author"
                  v-model="author"
                />
              </div>
              <div class="form-group">
                <label for="desk">Deskripsi</label>
                <textarea
                  class="form-control"
                  name="desc"
                  placeholder="deskripsi"
                  v-model="desc"
                ></textarea>
              </div>
            </form>
            <form class="d-flex">
              <button @click="back" class="back-button btn btn-secondary">
                Kembali
              </button>
              <button @click="save" class="save-btn btn btn-secondary justify-content-md-end">
                Simpan
              </button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import DataService from "../views/DataService";
export default {
  name: "tambuku",
  data() {
    return {
      tambuku: {
        id: null,
        Judul: "",
        isbn: "",
        author: "",
        deskripsi: "",
        published: false,
      },
      submitted: false,
    };
  },
  methods: {
    save() {
      var data = {
        Judul: this.Judul,
        isbn: this.isbn,
        author: this.author,
        deskripsi: this.deskripsi,
      };
      DataService.create(data)
        .then((response) => {
          this.DataView.id = response.data.id;
          console.log(response.data);
          this.submitted = true;
        })
        .catch((e) => {
          console.log(e);
        });
    },

    newTutorial() {
      this.submitted = false;
      this.tutorial = {};
    },
  },
};
</script>

<style>
div .container {
  padding: 50px;
}
.form-group {
  padding: 0px 10px 8px;
}
button {
  margin: 0px 10px;
}
.modal-footer p {
  padding: 0px 6px;
}
</style>
