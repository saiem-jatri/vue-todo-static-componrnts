<template>
    <div>
        <button class="px-4 py-2 bg-[#3a0061] border border-[rgb(58,0,97)] text-white cursor-pointer" :class="mode">
            <slot></slot>
        </button>
    </div>
</template>
<script>

export default {
    props:['mode']
}
</script>


<style>
.flat{
    background-color:transparent ;
    color:#3a0061;
    border:none;
}

.flat:hover,
.flat:active{
    background-color: #edd2ff;
}
</style>