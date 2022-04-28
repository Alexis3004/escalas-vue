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
            <table>
                <thead>
                    <tr>
                        <td>Habla</td>
                        <td></td>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>

                        </td>
                        <td>

                        </td>
                    </tr>
                </tbody>
            </table>
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

        const inputModelHabla = ref([
            {
                criterio: "Disartria: Alteración articulación de la palabra",
                puntaje: "",
                key: "disartria_habla",
                observaciones: [
                    {
                        nombre: "",
                        puntaje: "",
                    },
                    {
                        nombre: "Sí",
                        puntaje: "1",
                    },
                    {
                        nombre: "No",
                        puntaje: "2",
                    }
                ],
            },
            {
                criterio: "Disfonía: Alteración del tono de la voz",
                puntaje: "",
                key: "disfonia_habla",
                observaciones: [
                    {
                        nombre: "",
                        puntaje: "",
                    },
                    {
                        nombre: "Sí",
                        puntaje: "1",
                    },
                    {
                        nombre: "No",
                        puntaje: "2",
                    }
                ],
            },
            {
                criterio: "Afasia: Alteración o pérdida del lenguaje por daño cerebral",
                puntaje: "",
                key: "afasia_habla",
                observaciones: [
                    {
                        nombre: "",
                        puntaje: "",
                    },
                    {
                        nombre: "Sí",
                        puntaje: "1",
                    },
                    {
                        nombre: "No",
                        puntaje: "2",
                    }
                ],
            },
        ]);

        const inputModelLenguaje = ref([
            {
                criterio: "Hallazgos de la memoria",
                puntaje: "",
                key: "hallazgos_lenguaje",
                observaciones: [
                    {
                        nombre: "Seleccionar",
                        puntaje: "",
                    },
                    {
                        nombre: "Comprensión: Entiende y ejecuta órdenes",
                        puntaje: "1",
                    },
                    {
                        nombre: "Espontáneo: Normal 50 palabras por minuto",
                        puntaje: "2",
                    },
                    {
                        nombre: "Lecto-escritura: Lee un texto y escribe una frase ideada por él",
                        puntaje: "3",
                    },
                    {
                        nombre: "Nominación: Nombra objetos conocidos al mostrárselos",
                        puntaje: "4",
                    },
                    {
                        nombre: "Repetición: Repite palabras y frases de complejidad creciente",
                        puntaje: "5",
                    },
                    {
                        nombre: "Sin alteraciones",
                        puntaje: "0",
                    }
                ],
            },
            {
                criterio: "Observaciones:",
                puntaje: "",
                key: "observaciones_habla_lenguaje",
            }
        ])

        const limpiarCampos = () => {
            inputModelHabla.value.forEach((item) => {
                item.puntaje = ''
            })
        }

        const getData = () => {
            return {
                tarjeta: 'hallazgos_memoria',
                model: {
                    hallazgos_memoria: inputModelHabla.value[0].puntaje,
                    observaciones: inputModelHabla.value[1].puntaje
                }

            }
        }

        return {
            backup,
            inputModelHabla,
            inputModelLenguaje,
            limpiarCampos,
            getData,
        };
    },
};
</script>

<style></style>
