<template>
    <header class="header header--transp">
        <div class="container">
            <div class="header__inner">
                <div class="logo header__logo"><span class="logo__firstLetter">I</span>skra</div>
                <ul class="menu-nav header__nav">
                    <li class="menu-nav__li" v-for="item in items" :key="item"><a href="#">{{ item }}</a></li>
                </ul>
                <div class="login header__login">
                    <button class="btn btn--transp" data-toggle="modal" data-target="#exampleModal">Вход</button>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
    export default {
        name: 'Header',
        data() {
            return {
                items: ['Новости', 'Расписание', 'Оплата', 'Галерея', 'Контакты']
            }
        }
    }
</script>
