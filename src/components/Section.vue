<template>
    <div id="nota">
        <div class="input-group mb-3">
            <input class="form-control" id="tarea" placeholder="    ¿Qué quieres recordar?" v-model="tareaModel" type="text" name="tarea" v-on:keyup.13="anadirNota">
        </div>
        <div id="contadoresTareas">
            <hr>
            <p>Tareas pendientes de un total de {{notas.length}} | <a id="borrarCompletadas">Borras tareas completadas</a></p>
            <hr>
        </div>
        <div>
            <ul class="list-group">
                <li class="list-group-item li" v-for="nota in notas">
                    <div class="custom-control custom-checkbox">
                        <ion-icon name="checkmark-circle"></ion-icon>
                        <h1>{{ nota.tarea }}</h1>
                        <br>
                    </div>
                    <div>Prioridad:
                        <div class="btn-group btn-group-toggle" data-toggle="buttons">
                            <label class="btn btn-secondary active">
                                <input type="radio" name="options" id="low" autocomplete="off" checked> Low
                            </label>
                            <label class="btn btn-secondary">
                                <input type="radio" name="options" id="normal" autocomplete="off"> Normal
                            </label>
                            <label class="btn btn-secondary">
                                <input type="radio" name="options" id="high" autocomplete="off"> High
                            </label>
                        </div>
                        Fecha de creación: {{ nota.fechaCreacion }}
                    </div>
                </li>
            </ul>
        </div>
    </div>

</template>

<script>
    export default {
        name: "Section",
        data: function(){
            return {
                notas: [],
                tareaModel: "",
                prioridadModel: "",
            }
        },
        methods:{
            anadirNota: function () {
                var notaNueva = {
                    tarea: this.tareaModel,
                    prioridad: this.prioridadModel,
                    fechaCreacion: new Date().toLocaleString(),
                    completada: "No completada",
                };
                this.notas.push(notaNueva);
                this.tareaModel="";
                this.prioridadModel="";
                localStorage.setItem('tareas', JSON.stringify(this.notas));
            },
            completarTarea: function () {
                this.completada="Completada";
            },
            contarCompletadas: function () {

            }
        },
        mounted(){
            if (localStorage.getItem('tareas')){
                this.notas = JSON.parse(localStorage.getItem('tareas'));
            }
        }
    }
</script>

<style scoped>
    #contadoresTareas{
        color: white;
    }
    hr{
        background: #3D3D3D;
    }
    #tarea{
        width: 100%;
        height: 55px;
    }
    #borrarCompletadas{
        color: #E89613;
    }
    .li{
        padding-left: 40px;
        background: #303030;
        color:white;
        border-color: #3D3D3D;
    }
</style>