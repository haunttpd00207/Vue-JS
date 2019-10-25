<template>
    <aside class="sm-side">
        <div class="user-head">
            <img src="src/assets/images/profile.jpg">

            <div class="user-name">
                <h5>Bo Andersen</h5>
                <span class="email-address">info@codingexplained.com</span>
            </div>
        </div>

        <ul class="inbox-nav">
            <li class="active">
                <a href="#" @click.prevent="navigate_menu('app-inbox', 'Inbox')">
                    <i class="fa fa-inbox"></i>Inbox <span class="label label-danger pull-right">?</span>
                </a>
            </li>

            <li>
                <a href="#" @click.prevent="navigate_menu('app-sent', 'Sent')">
                    <i class="fa fa-envelope-o"></i>Sent <span class="label label-default pull-right">?</span>
                </a>
            </li>

            <li>
                <a href="#" @click.prevent="navigate_menu('app-important', 'Important')">
                    <i class="fa fa-bookmark-o"></i>Important <span class="label label-warning pull-right">?</span>
                </a>
            </li>

            <li>
                <a href="#" @click.prevent="navigate_menu('app-trash', 'Trash')">
                    <i class=" fa fa-trash-o"></i>Trash <span class="label label-default pull-right">?</span>
                </a>
            </li>
        </ul>
    </aside>    
</template>
<script>
    import { eventBus } from './main';

    export default {
        props: {
            messages: {
                type: Object,
                required: true
            }
        },

        methods: {
            navigate_menu(newview, title){
                eventBus.$emit('changeView', {
                    tag: newview,
                    title: title
                });
            }
        },
        computed: {
            totalMessage: function() {

            },
            sentMessage: function(){

            },
            importantMessage: function(){

            },
            trashMessage: function(){

            }
        }

        }
</script>