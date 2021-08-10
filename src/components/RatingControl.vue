<template>
    <ul>
        <li :class="{active: activeOption === 'poor'}"><button type="button" @click="activate('poor')">Poor</button></li>
        <li :class="{active: activeOption === 'average'}"><button type="button" @click="activate('average')">Average</button></li>
        <li :class="{active: activeOption === 'great'}"><button type="button" @click="activate('great')">Great</button></li>
    </ul>
</template>
<script>
    import {
        ref
    } from 'vue';
    export default {
        setup() {
            const activeOption = ref(null);

            function activate(option) {
                activeOption.value = option
            }

            return {
                activeOption,
                activate
            };
        }
    }
</script>
<style lang="scss" scoped>
    .active {
        border: solid 2px teal;
    }
    
    button .active {
        border: solid 2px teal;
        color: teal;
    }
    
    ul {
        list-style: none;
        margin: 0.5rem 0;
        padding: 0;
        display: flex;
    }
    
    li {
        margin: 0 1rem;
        border: 1px solid #ccc;
        padding: 1rem;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    
    button {
        font: inherit;
        border: none;
        background-color: transparent;
        cursor: pointer;
    }
</style>