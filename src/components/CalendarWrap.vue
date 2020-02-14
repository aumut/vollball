<template>
    <div>
        <cal-rend/>
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

    }
}
</script>