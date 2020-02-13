<template>
    <div class="header__slider">
        <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
            <ol class="carousel-indicators">
                <li v-for="indicator in carousel_indicators" v-bind:key="indicator.index" data-target="#carouselExampleIndicators" v-bind:data-slide-to="indicator.index" v-bind:class="{ active: indicator.isActive }"></li>
            </ol>
            <div class="carousel-inner">
                <div class="carousel-item" v-for="item in carousel_items" :key="item.id" v-bind:class="{ active: item.isActive}">
                    <img class="d-block w-100 carousel-img" v-bind:src="require('../assets/images/content/' +  item.src)"  v-bind:alt="item.src">
                    <div class="carousel-caption carousel-text d-none d-md-block">
                        <h5 class="carousel-text__title">Играй с нами в <br> <span class="logo">Iskre</span></h5>
                        <p class="carousel-text__descr">{{ item.descr }}</p>
                    </div>
                </div>
            </div>
            <a v-for="carousel in carousel_controls" v-bind:key="carousel.text" v-bind:class="'carousel-control-' + carousel.data_slide" href="#carouselExampleIndicators" role="button" v-bind:data-slide="carousel.data_slide" >
                <span v-bind:class="'carousel-control-' + carousel.data_slide + '-icon'" aria-hidden="true"></span>
                <span class="sr-only">{{carousel.text}}</span>
            </a>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'HeaderSlider',
        data() {
            return {
                carousel_items: [
                    {
                        id: 1,
                        isActive: true,
                        src: 'slider_1.jpg',
                        descr: 'Волейбол моя жизнь, волейбол моя игра, с волейболом мы вместе, с волейболом навсегда'
                    },
                    {
                        id: 2,
                        isActive: false,
                        src: 'NatGeo06.jpg',
                        descr: 'Нет ничего лучше, чем прожить жизнь в стремлении стать совершеннее'
                    },
                    {
                        id: 3,
                        isActive: false,
                        src: 'NaturePatterns02.jpg',
                        descr: 'Каждая тренировка — это шаг вперед. Каждая пропущенная тренировка — это два шага назад'
                    },
                    {
                        id: 4,
                        isActive: false,
                        src: 'NatGeo17.jpg',
                        descr: 'Нет ничего лучше, чем прожить жизнь в стремлении стать совершеннее'
                    }
                ],
                carousel_controls: [
                    {
                        data_slide: 'prev',
                        text: 'Previous'
                    },
                    {
                        data_slide: 'next',
                        text: 'Next'
                    }
                ],
                carousel_indicators: [
                    {
                        index: 0,
                        isActive: true
                    },
                    {
                        index: 1,
                        isActive: false
                    },
                    {
                        index: 2,
                        isActive: false
                    }
                ]
            }
        }
    }
</script>
