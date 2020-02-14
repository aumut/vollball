<template>
    <content>
        <div class="page" v-for="page in page_list" v-bind:key="page.index">
            <h2 class="page__title">{{ page.title }}</h2>
            <div class="page__inner">
                <component :is="page.section"></component>
            </div>
        </div>
        <!-- here Ivan Calendaar -->
        <ivan-cal/>
    </content>
</template>
<script>
    import ContentNews from './ContentNews.vue';
    import ContentTimeTable from './ContentTimeTable.vue';
    // here Ivan Calendaar
    import IvanCal from './CalendarWrap';
    export default {
        name: 'Content',
        components: {
            // here Ivan Calendaar
            ContentNews, ContentTimeTable, IvanCal
        },
        data(){
            return {
                page_list: [
                    {
                        index: 1,
                        title: 'Новости',
                        section: ContentNews
                    },
                    {
                        index: 2,
                        title: 'Расписание',
                        section: ContentTimeTable
                    }
                ]
            }
        }
    }
</script>