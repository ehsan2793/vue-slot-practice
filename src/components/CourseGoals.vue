<template>
    <ul>
        <li v-for="goal in goals" :key="goal">
    <slot :goal='goal'/>
        </li>
    </ul>
</template>


<script>
export default {
    data(){
        return {
            goals:['learn' , 'learn more']
        }
    }
}
</script>
