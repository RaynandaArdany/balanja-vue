<template>
    <div v-if="getcategory == false">
        <div class="h-screen bg-white">
            <div class="flex justify-center items-center h-full">
                <img class="h-16 w-16" src="https://c.tenor.com/vVO4zUo9PRcAAAAC/guardian-tales.gif" alt="">
            </div>
        </div>
    </div>
    <div v-else>
        <div class="mt-20 text-center">
      <span class="font-bold text-4xl">Semua Kategori</span>
    </div>
    <div class="grid md:grid-cols-4 gap-3  mt-10 pl-5">
        <div v-for="category in getcategory">
 
            <article class="overflow-hidden rounded-lg shadow transition hover:shadow-lg">
                <img
                    alt="Office"
                    :src="category.banner"
                    class="h-56 w-full object-cover"
                />

                <div class="bg-white p-4 sm:p-6">
                    <time datetime="2022-10-10" class="block text-xs text-gray-500">
                    {{ category.slug }}
                    </time>

                    <a href="#">
                    <h3 class="mt-0.5 text-lg text-gray-900">
                        {{ category.name }}
                    </h3>
                    </a>
                </div>
                </article>

        
        </div>
        </div>



</div>
</template>
<script>
import { mapGetters, mapActions } from 'vuex';
    
    export default {
        computed: {
            ...mapGetters('category', ['getcategory']),
        },
        methods: {
            ...mapActions('category', ['fetchCategory']),
    },
    created(){
        this.fetchCategory();
    }
}
</script>