<template>
    <div class="row justify-content-center mt-5">
        <div class="col-6">
            <div class="row">
                <div class="col-12">
                    <label class="form-label" for="">Nueva tarea</label>
                    <div class="input-group">
                        <input class="form-control" type="text" v-model="newTask">
                        <button class="btn btn-info" @click="addTask">Agregar</button>
                    </div>
                </div>

                <div class="col-12 mt-5">
                    <table class="table table-hover">
                        <thead>
                            <tr>
                                <th>Tarea</th>
                                <th></th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="(task, index) in tasks" :key="index">
                                <td>{{ task }}</td>
                                <td class="text-end">
                                    <input type="checkbox" class="form-check-input">
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref } from "vue";

    const newTask = ref('');
    const tasks = ref([]);

    const addTask = () => {
        if(newTask.value.trim() !== ''){
            tasks.value.push(newTask.value);
            newTask.value = '';
        }
    }
</script>