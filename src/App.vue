<script setup>

const estado = reactive({
  numero1,
  numero2,
  operacao,
})

const EfetuaCalculo = () => {
  const { operacao } = estado;
  
  switch (operacao) {
    case 'adicao':
      return numero1 + numero2;
    case 'subtracao':
      return numero1 - numero2;
    case 'multiplicacao':
      return numero1 * numero2;
    case 'divisao':
      return numero1 / numero2;

  }
}
</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora aritmética</h1>
    </header>
    <form @submit="EfetuaCalculo">
      <div class="row">
        <div class="col-2">
          <input @change="evento => estado.numero1 = evento.target.value" required type="number" placeholder="Informe o 1º número" class="form-control" />
        </div>
        <div  @change="evento => estado.numero2 = evento.target.value" class="col-2">
          <input required type="number" placeholder="Informe o 2º número" class="form-control" />
        </div>
        <div class="col-2">
          <select @change="evento => estado.operacao = evento.target.value" class="form-control">
            <option value="adicao">Adição</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
          </select>
        </div>
        <div class="col-1">
          <button  class="btn btn-primary" type="submit">Calcular</button>
        </div>
        <div class="col-2">
          <label class=" p-2 bg-light" for="">res</label>
        </div>
      </div>
    </form>
  </div>
</template>

<style scoped></style>
