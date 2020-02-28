<template>
    <content>
        <!-- here Ivan Calendaar -->
        <ivan-cal/>
        <div class="page" v-for="page in page_list" v-bind:key="page.index">
            <h2 class="page__title">{{ page.title }}</h2>
            <div class="page__inner">
                <component :is="page.section"></component>
            </div>
        </div>
    </content>
</template>
<script>
    import ContentNews from './ContentNews.vue';
    import ContentTimeTable from './ContentTimeTable.vue';
    // here Ivan Calendaar
    import IvanCal from './CalendarWrap';
    import ContentPayment from './ContentPayment.vue';
    import ContentGallery from './ContentGallery.vue';
    import ContentContacts from "./ContentContacts";
    
    export default {
        name: 'Content',
        components: {
            // here Ivan Calendaar
            ContentNews, ContentTimeTable, IvanCal, ContentPayment, ContentGallery, ContentContacts
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
                    },
                    {
                        index: 3,
                        title: 'Оплата',
                        section: ContentPayment
                    },
                    {
                        index: 4,
                        title: 'Галерея',
                        section: ContentGallery
                    },
                    {
                        index: 5,
                        title: 'Контакты',
                        section: ContentContacts
                    }
                ]
            }
        }
    }
</script>