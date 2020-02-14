<template>
    <div class="container">
        <div class="footer__inner">
            <div class="footer__copyright">All rights reserved 2019</div>
            <ul class="social-menu">
                <li class="social-menu__li" v-for="social in social_list" v-bind:key="social.key">
                    <a href="#" v-bind:class="'social-menu__' + social.name">{{ social.name }}</a>
                </li>
            </ul>
            <ul class="footer-contacts">
                <li class="footer-contacts__li" v-for="contact in contact_list" v-bind:key="contact.index"><a href="#">{{contact.name}}</a></li>
            </ul>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'Footer',
        data() {
            return {
                social_list: [
                    { index: 1, name: 'fb' },
                    { index: 2, name: 'tw' },
                    { index: 3, name: 'inst' }
                ],
                contact_list: [
                    { index: 1, name: 'whatsapp'},
                    { index: 2, name: 'telegram'}
                ]
            }
        }
    }
</script>