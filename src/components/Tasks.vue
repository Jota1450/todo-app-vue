<template>
    <div class="card">
        <div class="card-content">
            <div class="block">
                <input class="input is-large" type="text" placeholder="Type a task 😁, then press enter ⌨️"
                    v-model="inputValue" v-on:keyup.enter="handleEnterPress" />
            </div>

            <div v-for="(task, index) in tasks" class="notification is-primary custom-box">
                <span>{{ index + 1 }}. {{ task.name }}</span>
                <span class="tag is-light" :class="task.finished ? 'is-primary' : 'is-danger'"
                    v-on:click="() => changeStatus(index, task.finished)">{{ task.finished ? 'Finished' : 'Pending'
                    }}</span>
                <div>
                    <span class="delete" v-on:click="() => deleteTask(index)"></span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            inputValue: "",
            tasks: [],
        };
    },
    methods: {
        handleEnterPress() {
            if (this.inputValue.replace(/\s/g, '') !== '') {
                this.tasks.push({ name: this.inputValue, finished: false });
                this.inputValue = ''
            }
        },
        deleteTask(index) {
            this.tasks.splice(index, 1)
        },
        changeStatus(index, currentState) {
            this.tasks[index].finished = !currentState
        }
    },
};
</script>

<style scoped>
input {
    text-align: center;
    font-size: 15px;
}

.tag {
    cursor: pointer;
}

.custom-box {
    display: flex;
    justify-content: space-between;
}
</style>
