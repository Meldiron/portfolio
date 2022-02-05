<template>
  <section class="flex space-x-0 sm:space-x-4">
    <div
      @click="toggleOpen()"
      v-bind:class="colorNameBg"
      class="
        hidden
        sm:flex
        select-none
        group
        cursor-pointer
        w-20
        h-20
        rounded-lg
        items-center
        justify-center
      "
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
        v-bind:class="colorNameText"
        class="
          w-8
          h-8
          transform
          group-hover:scale-125 group-hover:rotate-12
          transition
          duration-300
        "
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          :d="iconD"
        />
      </svg>
    </div>
    <div
      :id="'row-el-' + id"
      v-bind:style="{ maxHeight: isOpened ? getHeight() + 'px' : '80px' }"
      class="
        rounded-lg
        bg-white
        dark:bg-gray-800
        w-full
        p-6
        relative
        overflow-y-hidden
        duration-300
        shadow-md
      "
    >
      <div class="cursor-pointer flex items-start" @click="toggleOpen()">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          v-bind:class="colorNameText"
          class="
            block
            sm:hidden
            mr-2
            w-6
            h-6
            transform
            group-hover:scale-125 group-hover:rotate-12
            transition
            duration-300
          "
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            :d="iconD"
          />
        </svg>

        <h1
          v-bind:class="isOpened ? colorNameDark : ''"
          class="
            dark:text-gray-50
            text-black
            cursor-pointer
            font-bold
            uppercase
            text-md
            sm:text-2xl
            select-none
            pr-8
          "
        >
          {{ title }}
        </h1>
      </div>

      <div class="mt-8 dark:text-gray-300">
        <slot></slot>
      </div>

      <div
        @click="toggleOpen()"
        class="
          select-none
          cursor-pointer
          absolute
          right-0
          top-0
          w-20
          h-20
          flex
          justify-center
          items-center
        "
      >
        <svg
          v-bind:class="isOpened ? 'rotate-180' : ''"
          class="
            w-6
            h-6
            sm:w-8 sm:h-8
            text-gray-400
            hover:text-gray-600
            transform
            transition
            duration-300
          "
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M19 9l-7 7-7-7"
          />
        </svg>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  // colorNameBg = bg-x-200
  // colorNameText = text-x-600
  // colorNameDark = ? text-x-500 dark:text-x-400

  props: [
    'iconD',
    'colorNameBg',
    'colorNameText',
    'colorNameDark',
    'title',
    'id',
    'isOpened',
    'colorParent',
    'colorParent2',
  ],

  methods: {
    toggleOpen() {
      this.$emit('activate', {
        id: this.id,
        color: this.colorParent,
        color2: this.colorParent2,
      })
    },
    getHeight() {
      const el = document.querySelector('#row-el-' + this.id)

      if (!el) {
        return 0
      }

      return el.scrollHeight
    },
  },
})
</script>