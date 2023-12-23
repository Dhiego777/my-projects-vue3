<template>
    <task-box class="my-3 rounded-borders shadow-sm">
        <div class="row p-3">
            <div class="col">
                {{ task.description || 'Tarefa sem descrição'}}
            </div>
            <div class="col">
                <ProgressiveClock :timeInSeconds="task.durationInSeconds"></ProgressiveClock>
            </div>
        </div>
    </task-box>
</template>
<script>
import ProgressiveClock from './ProgressiveClock.vue';
import TaskBox from './TaskBox.vue';

export default {
    name:'AssignmentTask',
    components: {
        ProgressiveClock,
        TaskBox
    },
    props: {
        task: {
            type: Object,
            required: true
        }
    }
}
</script>

<style>
    .rounded-borders {
        border-radius: 7px;
    }
</style>