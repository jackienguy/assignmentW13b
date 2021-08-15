<template>
    <div>
        <button @click="notifyToggle">Change View</button>
    </div>
</template>

<script>
    export default {
        name: "ViewChange",
        props: {
            isGrid: Boolean
        },
        data: function() {
            return {
                displayView: {
                    'display': "none"
                }
            }
        },
        methods:  {
            notifyToggle: function() {
                console.log("emit happened");
                this.$root.$emit('toggleBtnClicked', this.displayView);
            } ,
            handleRootUpdate: function (displayView) {
                if(displayView == this.isGrid){
                    this.displayView = "grid"
                    console.log("the view change to grid");
                } 
            },
            handleViewChange: function() {
                this.displayView = {'display': this.isGrid};
            }      
        }
}
</script>

<style lang="scss" scoped>

</style>