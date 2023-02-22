<template>
    <div class="cell-12">
        <ul class="list-group">
            <li v-for="(item, index) in list" :class="[listClass, item.done ? 'done' : '']" :key="index">
                <span class="me-auto">{{ item.title }}</span>
                <div class="btn-group">
                    <button type="button" class="btn btn-success btn-sm"
                        @click="completeTask(item)">Concluir
                    </button>
                    <button type="button" class="btn btn-danger btn-sm"
                        @click="$emit('onDeleteItem', index)">Excluir
                    </button>
                </div>
            </li> 
        </ul>
    </div>
</template>
<script>
export default {
    props: ['list'],
    data() {
        return {
            listClass: 'list-group-item d-flex align-items-center'
        }
    },
    methods: {
        completeTask(item) {
            item.done = !item.done
        },
    },
}
</script>
<style>
    .done {
        background-color: lightGreen;
    }
</style>