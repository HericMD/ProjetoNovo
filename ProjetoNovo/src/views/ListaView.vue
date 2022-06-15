<script>
export default {
  data() {
    return {
      lista: [{ texto: "Fazer a lista de tarefas!" }],
      nova_tarefa: "",
    };
  },

  methods: {
    salvar() {
      this.lista.push({
        texto: this.nova_tarefa,
      });
      this.nova_tarefa = "";
    },
  },
};
</script>

<template>
  <h1>Lista de tarefas</h1>

  <div class="form">
    <input type="text" v-model="nova_tarefa" @keydown.enter="salvar" />
    <button @click="salvar">Salvar</button>
  </div>
  <div class="tabela">
    <table>
      <thead>
        <tr>
          <th>tarefas</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="tarefa in lista" :key="tarefa.texto">
          <td>{{ tarefa.texto }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style>
h1 {
  text-align: center;
}
.form {
  display: flex;
  justify-content: center;
}
.tabela {
  display: flex;
  text-align: center;
  justify-content: center;
}
</style>
