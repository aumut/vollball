<template>
    <div>
        <table class="table table-bordered time-table">
            <thead>
            <tr>
                <th>{{th_first}}</th>
                <th v-for="th in th_list" v-bind:key="th.index">{{ th.th_text }}</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="tr in tr_list" v-bind:key="tr.index">
                <td>{{ tr.time }}</td>
                <td v-for="th in th_list" v-bind:key="th.index">X</td>
            </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
    export default {
        name: 'ContentTimeTable',
        data() {
            return {


                isActive: true,
                th_first: 'Время / День',
                th_list: [
                    { index: 1, th_text: 'Пн'},
                    { index: 2, th_text: 'Вт'},
                    { index: 3, th_text: 'Ср'},
                    { index: 4, th_text: 'Чт'},
                    { index: 5, th_text: 'Пт'},
                    { index: 6, th_text: 'Сб'},
                    { index: 7, th_text: 'Вс'}
                ],
                tr_list: [
                    { index: 1, time: '16:00'},
                    { index: 2, time: '18:00'},
                    { index: 3, time: '20:00'}
                ]
            }
        }
    }
</script>