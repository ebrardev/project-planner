<template>
  <div class="filter-nav">
    <button class="ebrar-a" @click="updateFilter('all')" :class="{active:current === 'all'}"> All</button>
    <button class="ebrar-b" @click="updateFilter('active')"  :class="{active:current === 'active'}"> Active</button>
    <button  class="ebrar-c" @click="updateFilter('completed')"  :class="{active:current === 'completed'}"> Completed</button>
  </div>
</template>

<script>
export default {
    props:['current'],
    methods:{
        updateFilter(by){
            this.$emit("filterChange")
        }
    }

}
</script>

<style>

.ebrar-a{
    background-color: blue;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
    cursor: pointer;
    font-size: 1rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 0.1rem;
    transition: all 0.2s ease-in-out;
    border: none;
    outline: none;

}
.ebrar-b{
    background-color: green;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
    cursor: pointer;
    font-size: 1rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 0.1rem;
    transition: all 0.2s ease-in-out;
    border: none;
    outline: none;

}
.ebrar-c{
    background-color: red;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
    cursor: pointer;
    font-size: 1rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 0.1rem;
    transition: all 0.2s ease-in-out;
    border: none;
    outline: none;

}

.ebrar-a:hover{
    background-color: blue;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
    cursor: pointer;
    font-size: 1rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 0.1rem;
    transition: all 0.2s ease-in-out;
    border: none;
    outline: none;


}

.ebrar-b:hover{
    background-color: green;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
    cursor: pointer;
    font-size: 1rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 0.1rem;
    transition: all 0.2s ease-in-out;
    border: none;
    outline: none;

}

.ebrar-c:hover{
    background-color: red;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
    cursor: pointer;
    font-size: 1rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 0.1rem;
    transition: all 0.2s ease-in-out;
    border: none;
    outline: none;
}
</style>