<template>
<div class="bg-brand-red-light-1">
  <div class="py-6">
    <div class="text-left mb-4">
      <h2 class="text-3xl leading-loose text-brand-gray-dark-1 font-medium">Meet Our Interns</h2>
    </div>
    <div class="mb-4 border-b border-brand-red-light-3"></div>
    <div class="">
      <div class="lg:grid lg:grid-cols-3 gap-10">
        <div class="col-span-2">
            <div class="flex-col text-left">
              <h3 class=" text-brand-gray-light leading-tight py-4 mb-2">HIGHLIGHTS</h3>
              <p class="text-brand-gray-dark-1 text-justify">
                {{finalistDescription}}       
              </p>
            </div>
        </div>
        <div class="flex flex-col text-left mt-2">
          <div>
            <h3 class="pt-6 mb-2 text-brand-gray-light leading-tight">KEY STATS</h3>
          </div>
          <div class="flex flex-1 items-center">
            <div>
              <div class="flex flex-wrap lg:flex-row items-center space-x-2">
                <h1 class="text-3xl font-medium leading-loose text-brand-gray-dark-1 tracker-wide">{{ finalists }}</h1>
                <span class="uppercase text-brand-gray-light leading-tight text-base">Finalists</span>
              </div>
              <div class="flex flex-wrap lg:flex-row items-center space-x-2">
                <h1 class="text-3xl font-medium leading-loose text-brand-gray-dark-1 tracker-wide">$ {{ totalCombinedSalary }}</h1>
                <span class="uppercase text-brand-gray-light leading-tight text-base">In Monthly Income</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import { mapActions } from "vuex"
export default {
  props: {
    finalists: {
      type: Number,
      default: 0
    },
    totalCombinedSalary: {
      type: Number,
      default: 0
    },
    finalistDescription: {
      type: String,
      default: ""
    }
  },
  name: 'MeetOurIntern',
  data(){
    return {
      
    }
  },
  methods: {
    ...mapActions([ 'getTotalSalary'])
  },
  async created () {
    this.getTotalSalary()
  },
  computed: {
    totalSalary() {
      return this.$store.state.totalSalary
    }
  }
}
</script>