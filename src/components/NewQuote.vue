<template>
  <div>
    <div class="row">
        <textarea cols="100" rows="4" v-model="myQuote">{{ myQuote }}</textarea>
    </div>
    <div class="row">
        <button @click="addQuote">Add Quote</button>
    </div>
  </div>
</template>

<script>
export default {
    props: ['quotes'],
    data: function() {
        return {
            myQuote: ""
        }
    },
    methods: {
        addQuote: function() {
            if (this.myQuote && this.quotes.length < 10) {
                this.quotes.push(this.myQuote);
                this.myQuote = "";
            } else {
                this.$emit('updateView', "from NewQuote"); 
            }
        }
    }
}
</script>

<style>
</style>
