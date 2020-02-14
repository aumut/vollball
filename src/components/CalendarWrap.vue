<template>
    <div>
        <button @click="prevMonth">previous mon</button>
        <cal-rend :month="month" :year="year" :events="events"/>
        <button @click="nextMonth">next mon</button>
    </div>
</template>

<script>
import calRend from "./CalendarRender"
export default {
    name: 'CalendarWrap',
    components: { calRend },
    data: function() { return {
        month: 0,
        year: 2020,
        events: []
    }},
    methods: {
        // меняем месяц на предыдущий
        prevMonth() {
            if (this.month <= 0) {
                this.month = 11;
                this.year--;
            } else this.month--;
        },
        nextMonth() {
            alert('not implemented yet!');
        }
    }
}
</script>