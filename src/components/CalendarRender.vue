<template>
    <table>
        <th>
            <td>{{ month + "/" + year }}</td>
        </th>
            <!-- и рисуем всё из event -->
    </table>
</template>

<script>
export default {
    name: 'CalendarRender',
    props: {
        'month': Number,
        'year': Number,
        'events': Array
    },
    data: function() { return {
        
    }},
    methods: {

    }
}
</script>