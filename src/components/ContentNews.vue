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
    import news_list from '../assets/json/ContentNewsList';
    export default {
        name: 'ContentNews',
        data() {
            return {
                news_list: news_list
            }
        }
    }
</script>