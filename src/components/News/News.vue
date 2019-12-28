<template>
  <div class="row justify-content-center mb-4">
    <div class="col-md-9">
      <div class="card">
        <div class="card-body">
          <form>
            <h5>Adicione aqui seus amigos</h5>
            <div class="form-group">
              <label for="nomeJogo">Nick do Jogo</label>
              <input type="text" class="form-control" placeholder="Digite seu nome dentro do jogo" />
            </div>
            <a href="javascript:;" class="btn btn-primary" @click="addRow">Adicionar amigo</a>
          </form>

          <table class="table table-striped table-dark mt-4">
            <thead>
              <tr>
                <th scope="col">Nick name</th>
                <th scope="col">Date</th>
              </tr>
            </thead>
            <tbody>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    addRow() {}
  }
};
</script>

<style scoped>
h5,
label {
  color: rgb(82, 82, 82);
}
</style>
