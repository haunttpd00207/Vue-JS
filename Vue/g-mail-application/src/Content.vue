<template>
     <aside class="lg-side">
        <div class="inbox-head">
            <h3>{{ currentViewPost.title }}</h3>
        </div>
        <keep-alive>
            <component :is="currentViewPost.tag"></component>
        </keep-alive>
    </aside>
</template>
<script>
    import Inbox from "./Inbox.vue";
    import Sent from "./Sent.vue";
    import Important from "./Important.vue";
    import Trash from "./Trash.vue";
    import ViewMessage from "./ViewMessage.vue";
import { eventBus } from './main';

    export default {
        created(){
            eventBus.$on('changeView', (data) => {
                let temp = [{
                    tag: data.tag,
                    title: data.title
                }]; 
                this.history = temp.concat(this.history.splice(0));
            });
        },
        data() {
            return{
                history: [
                    {
                        tag: 'app-inbox',
                        title: 'Inbox'
                    }
                ]
            };
        },
        computed: {
            currentViewPost() {
                return this.history[0];
            }
        },
        components: {
            appInbox: Inbox,
            appSent: Sent,
            appImportant: Important,
            appTrash: Trash,
            appViewMessage: ViewMessage
        }
    }
</script>