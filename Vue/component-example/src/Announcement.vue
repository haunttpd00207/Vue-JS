<template>
    <div v-if="announcement">
        <div class="alert alert-info">{{ announcement }}</div>
    </div>
    <div v-else>
         <div class="alert alert-info">Unknow announcement</div>
    </div>
</template>

<script>
    import { eventBus } from './main';
    
    export default {
        data() {
            return {
                announcement: null
            }
        },
        created() {
            eventBus.$on('articleWasShared', (data) => {
               this.announcement = data.article.title + " was shared on " + data.media
            });
        }
    }
</script>