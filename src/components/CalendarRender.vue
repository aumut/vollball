<template>
    <table>
        <th>
            <td>{{ month + "/" + year }}</td>
        </th>
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