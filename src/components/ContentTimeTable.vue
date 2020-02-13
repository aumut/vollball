<template>
    <div>
        <table class="table table-bordered">
            <thead>
            <tr>
                <th v-for="col in col_list" v-bind:key="col.index">{{ col.col_text }}</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="row in rows_list" v-bind:key="row.index">
                <td v-for="col in columns"  v-bind:key="col.index">{{ columns }}</td>
                <!--<td v-for="td in td_list" v-bind:key="td.index">{{ td.date }}</td>-->
                <!--<td v-for="col in columns" v-bind:key="col.index">{{ row[col] }} </td>-->
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
                col_list: [
                    {
                        index: 1,
                        col_text: 'Пн'
                    },
                    {
                        index: 2,
                        col_text: 'Вт'
                    },
                    {
                        index: 3,
                        col_text: 'Ср'
                    },
                    {
                        index: 4,
                        col_text: 'Чт'
                    },
                    {
                        index: 5,
                        col_text: 'Пт'
                    },
                    {
                        index: 6,
                        col_text: 'Сб'
                    },
                    {
                        index: 7,
                        col_text: 'Вс'
                    }
                ],
                rows_list: [
                    {
                        index: 1,
                        row_text: '1122'
                    },
                    {
                        index: 2,
                        row_text: '444'
                    },
                    {
                        index: 3,
                        row_text: '444'
                    },
                    {
                        index: 4,
                        row_text: '444'
                    },
                    {
                        index: 5,
                        row_text: '444'
                    },
                    {
                        index: 6,
                        row_text: '444'
                    },
                    {
                        index: 7,
                        row_text: '444'
                    }
                ]
            }
        },
        computed: {
            "columns": function columns() {
                if (this.col_list.length == 0) {
                    return [];
                }
                return Object.keys(this.col_list[0])
            }
        }
    }
</script>