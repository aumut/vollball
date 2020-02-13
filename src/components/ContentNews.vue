<template>
    <div>
        <div class="article-list" v-for="news in news_list" v-bind:key="news.index">
            <div class="article-list__img"><img v-bind:src="require('../assets/images/content/' + news.img)"></div>
            <div class="article-list__info">
                <h3 class="article-list__title mb-2"><a href="#">{{ news.title}}</a></h3>
                <h4 class="article-list__subtitle mb-2"><a href="#">{{ news.subtitle }}</a></h4>
                <div class="article-list__details">
                    <span class="article-list__date">{{ news.date }}</span>
                    <span class="article-list__tag">{{ news.tag}}}</span>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'ContentNews',
        data() {
            return {
                news_list: [
                    {
                        index: 1,
                        img: 'slider_1.jpg',
                        title: 'Россия это сделала! Наши волейболисты смели всех и прорвались на Олимпиаду',
                        subtitle: 'Сборная России обыграла команду Ирана в трёх сетах. Соперники бились отчаянно, но устоять в Санкт-Петербурге не смогли.',
                        date: '6 сентября, 22:15',
                        tag: ' Сборная Россия'
                    },
                    {
                        index: 2,
                        img: 'slider_1.jpg',
                        title: 'Россия это сделала! Наши волейболисты смели всех и прорвались на Олимпиаду',
                        subtitle: 'Сборная России обыграла команду Ирана в трёх сетах. Соперники бились отчаянно, но устоять в Санкт-Петербурге не смогли.',
                        date: '6 сентября, 22:15',
                        tag: ' Сборная Россия'
                    },
                    {
                        index: 3,
                        img: 'slider_1.jpg',
                        title: 'Россия это сделала! Наши волейболисты смели всех и прорвались на Олимпиаду',
                        subtitle: 'Сборная России обыграла команду Ирана в трёх сетах. Соперники бились отчаянно, но устоять в Санкт-Петербурге не смогли.',
                        date: '6 сентября, 22:15',
                        tag: ' Сборная Россия'
                    },
                    {
                        index: 4,
                        img: 'slider_1.jpg',
                        title: 'Россия это сделала! Наши волейболисты смели всех и прорвались на Олимпиаду',
                        subtitle: 'Сборная России обыграла команду Ирана в трёх сетах. Соперники бились отчаянно, но устоять в Санкт-Петербурге не смогли.',
                        date: '6 сентября, 22:15',
                        tag: ' Сборная Россия'
                    },
                    {
                        index: 5,
                        img: 'slider_1.jpg',
                        title: 'Россия это сделала! Наши волейболисты смели всех и прорвались на Олимпиаду',
                        subtitle: 'Сборная России обыграла команду Ирана в трёх сетах. Соперники бились отчаянно, но устоять в Санкт-Петербурге не смогли.',
                        date: '6 сентября, 22:15',
                        tag: ' Сборная Россия'
                    }
                ]
            }
        }
    }
</script>