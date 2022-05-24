<template>
    <li class="mx-auto max-w-[640px] font-inter">
        <base-card>
            <header class="flex justify-between items-center">
                <h3 class="text-[24px] m-[8px]">{{title}}</h3>
                <base-button mode="flat" @click="deleteResource(id)">Delete</base-button>
            </header>
        
        <p class="m-[8px]">{{description}}</p>
        <nav>
            <a :href="link" class="outline-none text-[#ce5c00]">View Resources</a>
        </nav>
        </base-card>
    </li>
</template>
<script>
export default{
    props:['id','title','description','link'],
    inject:['deleteResource']
}

</script>

