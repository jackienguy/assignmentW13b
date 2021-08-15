<template>
    <div>
        <ul>
            <li>
                <p>{{ tweetContent }}</p> 
                <p>{{tweetUser}}</p>
                <p>{{tweetDate}}</p> 
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "TweetComp",
        props: {
            tweetContent: String,
            tweetUser: String,
            tweetDate: String,
            display: Boolean
        },
        mounted: function() {
            console.log();
            this.$root.$on('toggleBtnClicked', this.handleViewChange);
    } 
 }
</script>

<style scoped>
    li {
        border: 1px solid black;
        border-radius: 10px;
        list-style: none;
    }
</style>