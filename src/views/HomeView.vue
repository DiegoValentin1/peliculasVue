<template>
  <div>
    <h1>Peliculas</h1>
    <div>
      <b-button v-b-modal.modal-p>Agregar Pelicula</b-button>

      <b-modal id="modal-1" title="BootstrapVue">
        <p class="my-4">Hello from modal!</p>
      </b-modal>
      <b-modal id="modal-m" title="Modificar Pelicula">
        <div>
          <b-form @submit="onSubmit" @reset="onReset" v-if="show">
            <b-form-group
              id="input-group-2"
              label="Nombre:"
              label-for="input-2"
            >
              <b-form-input
                id="input-2"
                v-model="form.name"
                placeholder="Enter nombre"
                required
              ></b-form-input>
            </b-form-group>

            <b-form-group
              id="input-group-3"
              label="Director:"
              label-for="input-3"
            >
              <b-form-input
                id="input-3"
                v-model="form.director"
                placeholder="Enter director"
                required
              ></b-form-input>
            </b-form-group>

            <b-form-group
              id="input-group-3"
              label="Duración:"
              label-for="input-3"
            >
              <b-form-input
                id="input-3"
                v-model="form.duracion"
                placeholder="Enter duración"
                required
              ></b-form-input>
            </b-form-group>

            <b-form-group
              id="input-group-4"
              label="Genero:"
              label-for="input-4"
              class="mb-3"
            >
              <b-form-select
                id="input-4"
                v-model="form.food"
                :options="foods"
                required
              ></b-form-select>
            </b-form-group>

            <b-button type="submit" variant="primary">Submit</b-button>
            <b-button type="reset" variant="danger">Reset</b-button>
          </b-form>
        </div>
      </b-modal>
      <b-modal id="modal-p" title="Agregar Pelicula">
        <div>
          <b-form @submit="onSubmit" @reset="onReset" v-if="show">
            <b-form-group
              id="input-group-2"
              label="Nombre:"
              label-for="input-2"
            >
              <b-form-input
                id="input-2"
                v-model="form.name"
                placeholder="Enter nombre"
                required
              ></b-form-input>
            </b-form-group>

            <b-form-group
              id="input-group-3"
              label="Director:"
              label-for="input-3"
            >
              <b-form-input
                id="input-3"
                v-model="form.director"
                placeholder="Enter director"
                required
              ></b-form-input>
            </b-form-group>

            <b-form-group
              id="input-group-3"
              label="Duración:"
              label-for="input-3"
            >
              <b-form-input
                id="input-3"
                v-model="form.duracion"
                placeholder="Enter duración"
                required
              ></b-form-input>
            </b-form-group>

            <b-form-group
              id="input-group-4"
              label="Genero:"
              label-for="input-4"
              class="mb-3"
            >
              <b-form-select
                id="input-4"
                v-model="form.food"
                :options="foods"
                required
              ></b-form-select>
            </b-form-group>

            <b-button type="submit" variant="primary">Submit</b-button>
            <b-button type="reset" variant="danger">Reset</b-button>
          </b-form>
        </div>
      </b-modal>
    </div>
    <div id="mainPeliculas">
      <div>
        <b-card-group deck>
          <b-card title="Titanic" header-tag="header" footer-tag="footer">
            <b-card-text>Director</b-card-text>
            <b-card-text>Duración</b-card-text>
            <b-card-text>Genero</b-card-text>
            <template #header>
              <b-container align-h="center">
              <b-row>
                <b-col>
                  <b-button href="#" variant="warning" v-b-modal.modal-m
                    >Editar</b-button
                  >
                  <b-button href="#" variant="danger" v-b-modal.modal-m
                    >Eliminar</b-button
                  >
                </b-col>
              </b-row>
            </b-container>
            </template>
          </b-card>
        </b-card-group>
      </div>
      <div>
        <b-card-group deck>
          <b-card title="Titanic" header-tag="header" footer-tag="footer">
            <b-card-text>Director</b-card-text>
            <b-card-text>Duración</b-card-text>
            <b-card-text>Genero</b-card-text>
            <template #header>
              <b-container align-h="center">
              <b-row>
                <b-col>
                  <b-button href="#" variant="warning" v-b-modal.modal-m
                    >Editar</b-button
                  >
                  <b-button href="#" variant="danger" v-b-modal.modal-m
                    >Eliminar</b-button
                  >
                </b-col>
              </b-row>
            </b-container>
            </template>
          </b-card>
        </b-card-group>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: "",
        director: "",
        food: null,
        duracion: "",
      },
      foods: [
        { text: "Select One", value: null },
        "Terror",
        "Suspenso",
        "Comedia",
        "Romance",
      ],
      show: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.director = "";
      this.form.name = "";
      this.form.duracion = "";
      this.form.genero = "";
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>

<style>
</style>