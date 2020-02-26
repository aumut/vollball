<template>
    <table>
        <th>
            <td @click="clickOnDay">{{ month + "/" + year }}</td>
        </th>
            <!-- и рисуем всё из event -->
            <tr />
    </table>
</template>

<script>
export default {
    name: 'CalendarRender',
    props: {
        'month': Number,
        'year': Number,
        'events': Array,
        'mon': Array
    },
    data: function() { return {
        ourMonth: []
    }},
    methods: {
        init() {
            this.createMonth();
        },
        createMonth() {
            // тут создаем массив на месяц
            let dstr = (this.month < 10 ? "0" : "")
                + (1 + this.month).toString() + "/01" + "/" + this.year.toString();
            let begin = new Date(dstr);
            let firstDayOfMon = begin.getDay();
            alert(dstr + " " + firstDayOfMon);
            alert(this.mon);

            if (firstDayOfMon === '1') { // 1=mond
                this.createWeek(firstDayOfMon);
            } else { console.log("not ready"); }
            for(let i = firstDayOfMon + 7; i < this.mon; i++) {
                ;
            }
            alert(this.ourMonth);
        },
        createWeek(startDay) {
            // тут делаем неделю
            let thr = startDay + 7;
            let week = [];
            for (let i = startDay; i < thr; i++) {
                week.push( {day: i} );
            }
            this.ourMonth.push(week);
        },
        clickOnDay() {
            alert('clickOnDay');
            this.$emit('clickOnDay', 'myMeSSAGE');
        }
    },
    mounted() {
        this.init();
    }
}
</script>