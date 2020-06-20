<template>
  <div class="h-40 sm:h-64">
    <button
      @click="open"
      class="h-full w-full relative bg-cover bg-no-repeat bg-center group rounded-lg shadow-xl"
      :style="`background-image:url(/images/${image || 'default.jpg?webp'})`"
    >
      <div
        class="rounded-lg group-hover:opacity-100 opacity-0 absolute inset-0 bg-green-transparent transition duration-300 flex flex-col items-center justify-center"
      >
        <p class="text-white text-lg font-medium">{{ title }}</p>
        <p class="text-white text-lg mt-4">{{ company }}</p>
      </div>
    </button>

    <div
      ref="modal"
      v-if="showing"
      class="fixed inset-0 bg-black80 z-10 flex items-center justify-center lg:p-12"
    >
      <button @click="close" class="absolute top-0 right-0 m-4 hidden lg:block">
        <SvgClose class="text-gray-200 hover:text-gray-100" />
      </button>
      <div @click.stop class="bg-white w-full h-full flex-col lg:flex-row flex overflow-hidden lg:rounded-lg">
        <div class="flex-1 order-last relative overflow-auto p-4 sm:p-8 pb-24 lg:pb-8 overflow-x-hidden">
          <button class="fixed top-0 right-0 m-4 lg:hidden" @click="close">
            <SvgClose class="text-gray-700 hover:text-gray-800" />
          </button>
          <img
            class="mx-auto mt-12 lg:max-w-2xl"
            v-for="(display, index) in displays"
            :key="index"
            :src="`/images/${display}`"
            alt
          />
        </div>
        <ModalAccordion class="lg:hidden">
          <div>
            <p class="font-medium">Project Type</p>
            <p class="capitalize leading-none text-gray-700 text-sm">{{ type }}</p>
          </div>
          <div class="mt-8">
            <p class="font-medium">Project URL</p>
            <a class="hover:underline" target="__blank" v-if="url" :href="url">{{ url }}</a>
            <p v-else class="capitalize leading-none text-gray-700 text-sm">hidden</p>
          </div>
          <div class="mt-8">
            <p class="font-medium">Project Description</p>
            <p class="leading-snug text-gray-700 text-sm">{{ description }}</p>
          </div>
          <div class="mt-8">
            <p class="font-medium">My Contributions</p>
            <ul class="list-disc pl-4">
              <li class="leading-snug text-gray-700 text-sm" v-for="(contribution, index) in contributions" :key="index">{{ contribution }}</li>
            </ul>
          </div>
          <div class="mt-8">
            <p class="font-medium">Project Technologies</p>
            <div class="flex flex-wrap mt-1">
              <i
                v-for="technology in technologies"
                :key="technology"
                class="text-3xl colored mr-1 mt-1"
                :class="`devicon-${technology}-plain`"
              ></i>
            </div>
          </div>
        </ModalAccordion>
        <div class="w-88 border-l relative p-8 hidden lg:block shadow-xl">
          <div>
            <p class="font-bold text-xl">Project Type</p>
            <p class="capitalize leading-none text-gray-900 text-sm font-medium">{{ type }}</p>
          </div>
          <div class="mt-8">
            <p class="font-bold text-xl">Project URL</p>
            <a class="hover:underline" target="__blank" v-if="url" :href="url">{{ url }}</a>
            <p v-else class="capitalize leading-none text-gray-900 text-sm font-medium">hidden</p>
          </div>
          <div class="mt-8">
            <p class="font-bold text-xl">Project Description</p>
            <p class="leading-snug text-gray-900 text-sm font-medium">{{ description }}</p>
          </div>
          <div class="mt-8">
            <p class="font-bold text-xl">My Contributions</p>
            <ul class="list-disc">
              <li class="leading-snug text-gray-900 text-sm font-medium" v-for="(contribution, index) in contributions" :key="index">{{ contribution }}</li>
            </ul>
          </div>
          <div class="mt-8">
            <p class="font-bold text-xl">Project Technologies</p>
            <div class="flex flex-wrap mt-1">
              <i
                v-for="technology in technologies"
                :key="technology"
                class="text-3xl colored mr-1 mt-1"
                :class="`devicon-${technology}-plain`"
              ></i>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { disableBodyScroll, clearAllBodyScrollLocks } from "body-scroll-lock";
import ModalAccordion from "~/components/ModalAccordion";
import SvgClose from "~/components/Svg/SvgClose";

export default {
  props: {
    type: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      default: "default.jpg"
    },
    title: {
      type: String,
      required: false
    },
    company: {
      type: String,
      required: false
    },
    description: {
      type: String,
      required: true
    },
    contributions: {
      type: Array,
      required: true
    },
    technologies: {
      type: Array,
      required: false
    },
    displays: {
      type: Array,
      required: false
    },
    url: {
      type: String, 
    }
  },
  data: () => ({ showing: false }),
  components: { ModalAccordion, SvgClose },
  methods: {
    open() {
      this.showing = true;
      disableBodyScroll(this.$refs.modal);
    },
    close() {
      this.showing = false;
      clearAllBodyScrollLocks();
    }
  }
};
</script>