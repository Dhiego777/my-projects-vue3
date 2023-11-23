<template>
    <task-box>
        <div class="columns">
            <div class="column is-7">
                {{ task.description || 'Tarefa sem descrição'}}
            </div>
            <div class="column">
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