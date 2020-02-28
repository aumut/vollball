<template>
    <div>
        <button @click="prevMonth">previous mon</button>

        <cal-rend   :month="month"
                    :year="year"
                    :monthName="monthNames[month]"
                    :weeks="ourMonth"
                    v-on:clickOnDay="clickOnDayMethod"/>

        <button @click="nextMonth">next mon</button>
    </div>
</template>

<script>
import calRend from "./CalendarRender"
export default {
    name: 'CalendarWrap',
    components: { calRend },
    data() {
        return {
            // текущий месяц
            month: 0,
            // текущий год
            year: 2020,
            // дни в високосном году
            leapYearMonths: [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31],
            // дни в невисокосном году
            notLeapYearMonths: [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31],
            // названия месяцев
            monthNames: ['jan','feb','mar','apr','may','jun','jul','aug','sep','oct','nov','dec'],
            // названия дней недели
            dayNames: [], // TODO: заполнить здесь массив и вывести дни недели в календаре
            // ссылка либо на    leapYearMonths, либо на   notLeapYearMonths
            daysInMonths: null,
            // текущий месяц, в котором хранятся числа, и который передаем на отрисовку
            ourMonth: []
        }
    },
    methods: {
        // меняем месяц на предыдущий
        prevMonth() {
            if (this.month <= 0) {
                this.month = 11;
                this.year--;
                this.setLeapness();
            } else this.month--;
            this.ourMonth = this.createMonth();
        },
        // TODO: дописать этот метод (увеличение месяца)
        nextMonth() {
            alert('not implemented yet!');
        },
        // показывает, как работает emit
        clickOnDayMethod(message) {
            alert('в отрисовочном компоненте кликнули на: ' + message);
        },
        // тут создаем массив на месяц
        createMonth() {
            // этот массив заполним и вернем
            let mon = [];
            // строка с датой, для получения объекта Date на первый день нужного месяца
            let dstr = (this.month < 10 ? "0" : "")
                + (1 + this.month).toString() + "/01" + "/" + this.year.toString();
            let begin = new Date(dstr);
            // узнаем день недели у первого числа текущего месяца
            let firstDayOfMon = begin.getDay();
            // узнаем последнее число текущего месяца
            let curMonthLast = this.daysInMonths[this.month];
            // узнаем последнее число предыдущего месяца
            let lastMonthLast = this.daysInMonths[(this.month > 0 ? this.month - 1 : 11)];
            // сюда набираем неделю и кладем в массив месяца
            let week = [];
            // счетчик, сколько дней текущего месяца вставили в массив месяца
            let dayCnt = 0;
            
            if (firstDayOfMon !== '1') { // 1=понедельник, нет дне
                // сколько дней из предыдущего месяца надо добавить на первой неделе
                // если firstDayOfMon=0, но это воскресение, добавляем 6 дней в первую неделю, иначе считаем
                let missingDays = firstDayOfMon != 0 ? firstDayOfMon - 1: 6;
                for (let i = lastMonthLast - missingDays + 1; i <= lastMonthLast; i++)
                    week.push( {'day': i, 'pos': i} );
            }

            // несколько раз добавляем по неделе, пока счетчик дней не превысил кол-во дней в месяце
            while (dayCnt < this.daysInMonths[this.month]) {
                for (let i = week.length; i < 7; i++) {
                    // если кол-во дней превысило месячное, то начинаем добавлять 1, 2, 3...
                    week.push( {'day': (++dayCnt <= curMonthLast ? dayCnt : dayCnt - curMonthLast), 'pos': i} );
                }
                mon.push( {'week': week, pos: dayCnt / 7} );
                week = [];
            }
            
            return mon;
        },
        // проверяет, високосный ли год
        isLeapYear(year) { // TODO доделать проверку на високосность года (она неполная)
            return year % 4;
        },
        setLeapness() {
            if (this.isLeapYear(this.year)) this.daysInMonths = this.leapYearMonths;
            else this.daysInMonths = this.notLeapYearMonths;
        }
    },
    // хук на создание данного вуэ-компонента
    created() {
        // берем текущую дату и у неё текущ.месяц
        let curDate = new Date();
        
        this.month = curDate.getMonth();
        this.year = curDate.getFullYear();

        // проверка на високосн., сослаться нужный месяц
        this.setLeapness();

        this.ourMonth = this.createMonth();
    }
}
</script>