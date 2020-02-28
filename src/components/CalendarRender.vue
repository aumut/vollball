<template>
    <table>
    <thead>
        <th colspan="7">
            <td>{{ monthName + " / " + year }}</td>
        </th>
    </thead>
    <tbody>
        <!-- и рисуем всё из weeks -->
        <tr v-for="week in weeks" :key="week.pos">
            <td v-for="day in week.week" :key="day.pos" style="padding-left: 5px"
                 @click="clickOnDay(day.day)">{{ day.day }}</td>
        </tr>
    </tbody>
    </table>
</template>

<script>
export default {
    name: 'CalendarRender',
    props: {
        // номер месяца, 0-11
        'month': Number,
        // месяц текстом
        'monthName': String,
        // год
        'year': Number,
        // наши недели
        'weeks': Array
    },
    methods: {
        // событие на клик по числу в календаре
        clickOnDay(day) {
            // передаем информацию (число, по кот. кликнули) в родительский компонент
            this.$emit('clickOnDay', day);
        }
    },
    mounted() {
        // console.log(this.year, this.month);
    }
}
</script>