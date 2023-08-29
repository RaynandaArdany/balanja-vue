<template>
    <div v-if="getBrands == false">
        <div class="h-screen bg-white">
            <div class="flex justify-center items-center h-full">
                <img class="h-16 w-16" src="https://c.tenor.com/vVO4zUo9PRcAAAAC/guardian-tales.gif" alt="">
            </div>
        </div>
    </div>
    <div v-else>
        <div class="mt-20 text-center">
      <span class="font-bold text-4xl">Semua Brads</span>
    </div>
    <div class="grid md:grid-cols-4 gap-3  mt-10 pl-5">
        <div v-for="brands in getBrands.data.slice(0, 12)" :key="brands.id">
            <!-- component -->
            <a href="#" class="block rounded-lg p-4 shadow-sm shadow-indigo-100">
  <img
    alt="Home"
    :src="brands.logo"
    class="h-56 w-full rounded-md object-cover"
  />

  <div class="mt-2">
    <dl>
      <div>
        <dt class="sr-only">Price</dt>

        <dd class="text-sm text-gray-500">{{ brands.slug }}</dd>
      </div>

      <div>
        <dt class="sr-only"></dt>

        <dd class="font-medium">{{ brands.name }}</dd>
      </div>
    </dl>
  </div>
</a>

            </div>
        </div>



</div>
</template>
 <script>
      import { mapGetters, mapActions } from 'vuex'; 
      export default{
          computed: {
              ...mapGetters('brands', ['getBrands']),
          },
          methods: {
              ...mapActions('brands', ['fetchBrands'])
          },
          created() {
              this.fetchBrands();
          },
      }
   </script>