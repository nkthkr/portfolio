<template>
  <FadeIn>
    <div
      class="max-w-full sm:w-sm mx-auto bg-gray-800 shadow-2xl rounded-lg overflow-hidden"
    >
      <div class="py-3 px-4 flex">
        <div class="rounded-full w-3 h-3 bg-red-500 mr-2"></div>
        <div class="rounded-full w-3 h-3 bg-yellow-500 mr-2"></div>
        <div class="rounded-full w-3 h-3 bg-green-500"></div>
      </div>
      <div class="py-4 px-4 mt-1 text-white text-xs md:text-base">
        <div class="mb-2">
          <span class="text-yellow-300">data ( )</span>
          <span class="ml-2">{</span>
        </div>

        <div class="mb-2 ml-2 md:ml-4">
          <span class="text-yellow-600">return</span>
          <span class="ml-2">{</span>
        </div>

        <div class="mb-2 ml-4 md:ml-8">
          <span class="text-blue-300">Name</span>
          <span class="mr-2">:</span>
          <span class="text-green-300">' Hikaru Nakata '</span>
          <span>,</span>
        </div>

        <div class="mb-2 ml-4 md:ml-8">
          <span class="text-blue-300">School</span>
          <span class="mr-2">:</span>
          <span class="text-green-300">' Doshisha Univ Grad School '</span>
          <span>,</span>
        </div>

        <div class="mb-2 ml-4 md:ml-8">
          <span class="text-blue-300">DateOfBirth</span>
          <span class="mr-2">:</span>
          <span class="text-green-300">' 1997-7-17 '</span>
          <span>,</span>
        </div>

        <div class="mb-2 ml-4 md:ml-8">
          <span class="text-blue-300">Skills</span>
          <span class="mr-2">:</span>
          <span>[</span>
        </div>

        <div class="mb-2 ml-6 md:ml-12">
          <span class="text-green-300">' Frontend '</span>
          <span class="mr-2">,</span>
        </div>

        <div class="mb-2 ml-6 md:ml-12">
          <span class="text-green-300">' UI / UX '</span>
          <span class="mr-2">,</span>
        </div>

        <div class="mb-2 ml-6 md:ml-12">
          <span class="text-green-300">' Web Accessibility '</span>
          <span class="mr-2">,</span>
        </div>

        <div class="mb-2 ml-4 md:ml-8">
          <span>] ,</span>
        </div>

        <div class="mb-2 ml-2 md:ml-4">
          <span>}</span>
        </div>

        <div class="mb-2">
          <span>} ,</span>
        </div>
      </div>
    </div>
  </FadeIn>
</template>

<script>
import FadeIn from '@/components/atoms/FadeIn'

export default {
  components: {
    FadeIn,
  },
}
</script>
