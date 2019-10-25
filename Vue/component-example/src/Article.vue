<template>
    <div class="article">
        <h1 v-once>{{ title }}</h1>

        <p>Published on {{ published | moment }}</p>
        <p>was shared x{{ shares }}</p>
        <p class="lead">{{ content }}</p>
        <app-author :author="author"></app-author>
        <br><br>

        <app-social-sharing :article="$data" @articleWasShared="shared($event)"></app-social-sharing>
        <br><br>
        <app-contact>
            <p slot="top">Leave a message and we gonna contact you as soon as possible</p>
            <p slot="bottom">Please do not submit any dirty information </p>
        </app-contact>
    </div>
</template>

<script>
    import moment from 'moment';
    import Author from './Author.vue';
    import Social from './Social.vue';
    import Contact from './Contact.vue';

    export default {
        data() {
            return {
                title: '10 Reasons why Vue.js is Awesome',
                published: new Date(),
                content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla accumsan eu erat ut scelerisque.',
                author: {
                    firstName: 'Bo',
                    lastName: 'Andersen'
                },
                shares: 0
            };
        },
        methods: {
            shared: function($event){
                this.shares++;
            }
        },
        filters: {
            moment: function(value) {
                return moment(value).format('MMMM Do');
            }
        },
        components: {
            appAuthor: Author,
            appSocialSharing: Social,
            appContact: Contact
        }
    }
</script>