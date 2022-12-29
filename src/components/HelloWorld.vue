<script>
import "bootstrap/dist/css/bootstrap.css";
export default {
  data() {
    return {
      dataMahasiswa: [],
      nama: "",
      nim: "",
    };
  },
  methods: {
    simpanData() {
      var mahasiswa = {
        nama: this.nama,
        nim: this.nim,
      };
      this.dataMahasiswa.push(mahasiswa);
    },
  },
};
</script>

<template>
  <h1>Belajar form dan Vue Event</h1>

  <div class="container">
    <p class="alert alert-danger">Hello VueJs</p>
    <p>Nama</p>
    <input v-model="nama" type="text" class="form-text" />
    <p>Nim</p>
    <input v-model="nim" type="text" class="form-text" />
    <div class="mt-2">
      <button class="btn btn-info" type="submit" @click.prevent="simpanData">
        Simpan
      </button>
    </div>
  </div>

  <hr />
  <table class="table">
    <thead>
      <tr>
        <th>Nama</th>
        <th>Nim</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in dataMahasiswa" :key="item">
        <td>{{ item.nama }}</td>
        <td>{{ item.nim }}</td>
      </tr>
    </tbody>
  </table>
</template>