<template>
    <div>
        <button @click="prevMonth">previous mon</button>
        <cal-rend :month="month" :year="year" :events="events" 
            v-on:clickOnDay="clickOnDayMethod" :mon="mont"/>
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
        events: [],
        leapMon: [31, 29],
        notLeapMon: [31, 28, 31],
        mont: this.leapMon
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
        },
        clickOnDayMethod(message) {
            alert('clickOnDayMethod: ' + message);
        }
    },
    created() {            
        // берем текущую дату и у неё текущ.месяц
        let curDate = new Date();
        let curMon = curDate.getMonth();
        let curYear = curDate.getYear();
        console.log(curDate, curMon);
        this.month = curMon;
        // проверка на високосн., сослаться нужный месяц
        // if (isLeap(curYear)) this.mont = this.leapMon;
        // else this.mont = this.notLeapMon;
    }
}
</script>