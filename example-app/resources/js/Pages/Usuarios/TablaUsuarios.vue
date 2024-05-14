<template>
    <div class="flex flex-col">
      <div class="overflow-x-auto sm:-mx-6 lg:-mx-8">
        <div class="inline-block min-w-full py-2 sm:px-6 lg:px-8">
          <div class="overflow-hidden">
            <table class="min-w-full text-left text-sm font-light">
              <thead class="border-b font-medium dark:border-neutral-500">
                <tr>
                  <th scope="col" class="px-6 py-4">ID</th>
                  <th scope="col" class="px-6 py-4">Nombre</th>
                  <th scope="col" class="px-6 py-4">Correo</th>
                  <th scope="col" class="px-6 py-4">Fecha Creación</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="usuario in usuarios" :key="usuario.id" class="border-b dark:border-neutral-500">
                  <td class="whitespace-nowrap px-6 py-4 font-medium">{{usuario.id}}</td>
                  <td class="whitespace-nowrap px-6 py-4">{{usuario.name}}</td>
                  <td class="whitespace-nowrap px-6 py-4">{{usuario.email}}</td>
                  <td class="whitespace-nowrap px-6 py-4">@{{usuario.created_at}}</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </template>
  <script>
  export default {
    data() {
      return {
        usuarios: null,
      };
    },
    mounted() {
      let ruta1 = "usuarios";
      axios.get(ruta1).then((response) => {
        this.usuarios = response.data;
      });
    },
    methods: {
      ConsultaUsuarios() {
        let ruta1 = "usuarios";
        axios.get(ruta1).then((response) => {
          this.usuarios = response.data;
        });
      },
    },
  };
</script>