<template>
    <div class="card-body">
        <div class="pb-2 d-flex">
            <div class="me-auto">
                <span class="mcw-card-title"> Hallazgos de la memoria </span>
            </div>
            <div class="px-2 cursor-pointer">
                <i class="mcw-font-icon-size fas fa-caret-up"></i>
            </div>
        </div>
        <div class="mt-3 mcw-font-small card-gray">
            <div class="row">
                <div class="row">
                    <div class="col-2">
                        <span>
                            {{ inputModel[0].criterio }}
                        </span>
                    </div>
                    <div class="col-5">
                        <select name="" id="">
                            <option
                                v-for="(item, key) in inputModel[0]
                                    .observaciones"
                                :key="key"
                                value="item.puntaje"
                            >
                                {{ item.nombre }}
                            </option>
                        </select>
                    </div>
                </div>
                <div class="row">
                    <div class="col-12 text-start">
                        <span>{{ inputModel[1].criterio }}</span>
                        <textarea class="w-100" name="" id="" cols="30" rows="10" v-model="inputModel[1].puntaje">
                        </textarea>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { ref } from "vue";
export default {
    setup() {
        const backup = {
            hallazgos_memoria: '',
            observaciones: ''
        }

        const inputModel = ref([
            {
                criterio: "Hallazgos de la memoria",
                puntaje: "",
                key: "hallazgos_memoria",
                observaciones: [
                    {
                        nombre: "Seleccionar",
                        puntaje: "",
                    },
                    {
                        nombre: "Inmediata: Evolución de un estímulo (dígitos, palabras o letras)",
                        puntaje: "1",
                    },
                    {
                        nombre: "De corto plazo: Repite palabras y las recuerda después de 5 minutos",
                        puntaje: "2",
                    },
                    {
                        nombre: "De largo plazo: Recuerda hechos conocidos (nombres de presidentes, hechos deportivos, etc.)",
                        puntaje: "3",
                    },
                ],
            },
            {
                criterio: "Observaciones:",
                puntaje: "",
                key: "observaciones_hallazgos_memoria",
            },
        ]);

        const limpiarCampos = () => {
            inputModel.value.forEach((item) => {
                item.puntaje = ''
            })
        }

        const getData = () => {
            return {
                tarjeta: 'hallazgos_memoria',
                model: {
                    hallazgos_memoria: inputModel.value[0].puntaje,
                    observaciones: inputModel.value[1].puntaje
                }

            }
        }

        return {
            backup,
            inputModel,
            limpiarCampos,
            getData,
        };
    },
};
</script>

<style></style>
