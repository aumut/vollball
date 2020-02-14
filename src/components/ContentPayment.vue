<template>
    <div>
        <table class="table table-bordered payment">
            <thead>
            <tr>
                <th>{{th_first}}</th>
                <th v-for="th in th_list" v-bind:key="th.index">{{ th.th_text }}</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="tr in tr_list" v-bind:key="tr.index">
                <td>{{ tr.name }}</td>
                <td v-for="th in th_list" v-bind:key="th.index">X</td>
            </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
    export default {
        name: 'ContentPayment',
        data() {
            return {
                th_first: 'ФИО / Месяц',
                th_list: [
                    { index: 1, th_text: 'Янв.'},
                    { index: 2, th_text: 'Фев.'},
                    { index: 3, th_text: 'Мрт.'},
                    { index: 4, th_text: 'Апр.'},
                    { index: 5, th_text: 'Май.'},
                    { index: 6, th_text: 'Июн.'},
                    { index: 7, th_text: 'Июл.'},
                    { index: 8, th_text: 'Авг.'},
                    { index: 9, th_text: 'Сен.'},
                    { index: 10, th_text: 'Окт.'},
                    { index: 11, th_text: 'Нбр.'},
                    { index: 12, th_text: 'Дек.'}
                ],
                tr_list: [
                    { index: 1, name: 'Иванов И. И.'},
                    { index: 2, name: 'Иванов И. И.'},
                    { index: 3, name: 'Иванов И. И.'}
                ]
            }
        }
    }
</script>

