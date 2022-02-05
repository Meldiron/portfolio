<template>
  <div>
    <div
      v-bind:class="currentColor"
      class="fixed inset-0 p-4 bg-gradient-to-br"
    ></div>

    <div
      class="fixed left-0 z-10 items-center justify-center hidden w-full  top-8 sm:flex"
    >
      <div
        v-bind:class="currentColor2"
        class="w-40 h-3 rounded-full opacity-100"
      ></div>
    </div>

    <div
      id="page_wrapper"
      class="fixed p-4 overflow-y-scroll bg-gray-100  lg:left-4 lg:right-4 lg:top-4 lg:bottom-4 sm:left-2 sm:top-2 sm:right-2 sm:bottom-2 left-1 top-1 right-1 bottom-1 dark:bg-gray-900 rounded-xl"
    >
      <div class="flex flex-col items-center justify-center">
        <div
          class="flex flex-col items-center justify-center w-full max-w-6xl mt-0 space-x-4  lg:mt-32 sm:mt-16 sm:flex-row space-4 sm:items-between sm:justify-between"
        >
          <div class="flex mb-4 space-x-4 sm:mb-0">
            <button
              @click="onToggleDar()"
              v-if="isDark"
              class="p-2 text-gray-600 bg-gray-200 rounded-full  dark:bg-gray-800 hover:text-gray-900 dark:text-gray-100 dark:hover:text-gray-400"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-5 h-5"
                viewBox="0 0 20 20"
                fill="currentColor"
              >
                <path
                  d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"
                />
              </svg>
            </button>

            <button
              class="p-2 text-gray-600 bg-gray-200 rounded-full  dark:bg-gray-800 hover:text-gray-900 dark:text-gray-100 dark:hover:text-gray-400"
              @click="onToggleDar()"
              v-if="!isDark"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-5 h-5"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
                />
              </svg>
            </button>
          </div>

          <div class="flex space-x-4">
            <svg
              @click="goTo(gitHubUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-yellow-400 dark:hover:text-yellow-400"
              fill="currentColor"
              role="img"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>GitHub</title>
              <path
                d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"
              />
            </svg>

            <svg
              @click="goTo(messengerUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-yellow-400 dark:hover:text-yellow-400"
              fill="currentColor"
              role="img"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
            >
              <title>Messenger icon</title>
              <path
                d="M.001 11.639C.001 4.949 5.241 0 12.001 0S24 4.95 24 11.639c0 6.689-5.24 11.638-12 11.638-1.21 0-2.38-.16-3.47-.46a.96.96 0 00-.64.05l-2.39 1.05a.96.96 0 01-1.35-.85l-.07-2.14a.97.97 0 00-.32-.68A11.39 11.389 0 01.002 11.64zm8.32-2.19l-3.52 5.6c-.35.53.32 1.139.82.75l3.79-2.87c.26-.2.6-.2.87 0l2.8 2.1c.84.63 2.04.4 2.6-.48l3.52-5.6c.35-.53-.32-1.13-.82-.75l-3.79 2.87c-.25.2-.6.2-.86 0l-2.8-2.1a1.8 1.8 0 00-2.61.48z"
              />
            </svg>

            <svg
              @click="goTo(whatsappUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-yellow-400 dark:hover:text-yellow-400"
              fill="currentColor"
              role="img"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>WhatsApp icon</title>
              <path
                d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"
              />
            </svg>

            <svg
              @click="goTo(discordUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-yellow-400 dark:hover:text-yellow-400"
              fill="currentColor"
              role="img"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>Discord icon</title>
              <path
                d="M20.222 0c1.406 0 2.54 1.137 2.607 2.475V24l-2.677-2.273-1.47-1.338-1.604-1.398.67 2.205H3.71c-1.402 0-2.54-1.065-2.54-2.476V2.48C1.17 1.142 2.31.003 3.715.003h16.5L20.222 0zm-6.118 5.683h-.03l-.202.2c2.073.6 3.076 1.537 3.076 1.537-1.336-.668-2.54-1.002-3.744-1.137-.87-.135-1.74-.064-2.475 0h-.2c-.47 0-1.47.2-2.81.735-.467.203-.735.336-.735.336s1.002-1.002 3.21-1.537l-.135-.135s-1.672-.064-3.477 1.27c0 0-1.805 3.144-1.805 7.02 0 0 1 1.74 3.743 1.806 0 0 .4-.533.805-1.002-1.54-.468-2.14-1.404-2.14-1.404s.134.066.335.2h.06c.03 0 .044.015.06.03v.006c.016.016.03.03.06.03.33.136.66.27.93.4.466.202 1.065.403 1.8.536.93.135 1.996.2 3.21 0 .6-.135 1.2-.267 1.8-.535.39-.2.87-.4 1.397-.737 0 0-.6.936-2.205 1.404.33.466.795 1 .795 1 2.744-.06 3.81-1.8 3.87-1.726 0-3.87-1.815-7.02-1.815-7.02-1.635-1.214-3.165-1.26-3.435-1.26l.056-.02zm.168 4.413c.703 0 1.27.6 1.27 1.335 0 .74-.57 1.34-1.27 1.34-.7 0-1.27-.6-1.27-1.334.002-.74.573-1.338 1.27-1.338zm-4.543 0c.7 0 1.266.6 1.266 1.335 0 .74-.57 1.34-1.27 1.34-.7 0-1.27-.6-1.27-1.334 0-.74.57-1.338 1.27-1.338z"
              />
            </svg>

            <svg
              @click="goTo(igUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-yellow-400 dark:hover:text-yellow-400"
              fill="currentColor"
              role="img"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>Instagram icon</title>
              <path
                d="M12 0C8.74 0 8.333.015 7.053.072 5.775.132 4.905.333 4.14.63c-.789.306-1.459.717-2.126 1.384S.935 3.35.63 4.14C.333 4.905.131 5.775.072 7.053.012 8.333 0 8.74 0 12s.015 3.667.072 4.947c.06 1.277.261 2.148.558 2.913.306.788.717 1.459 1.384 2.126.667.666 1.336 1.079 2.126 1.384.766.296 1.636.499 2.913.558C8.333 23.988 8.74 24 12 24s3.667-.015 4.947-.072c1.277-.06 2.148-.262 2.913-.558.788-.306 1.459-.718 2.126-1.384.666-.667 1.079-1.335 1.384-2.126.296-.765.499-1.636.558-2.913.06-1.28.072-1.687.072-4.947s-.015-3.667-.072-4.947c-.06-1.277-.262-2.149-.558-2.913-.306-.789-.718-1.459-1.384-2.126C21.319 1.347 20.651.935 19.86.63c-.765-.297-1.636-.499-2.913-.558C15.667.012 15.26 0 12 0zm0 2.16c3.203 0 3.585.016 4.85.071 1.17.055 1.805.249 2.227.415.562.217.96.477 1.382.896.419.42.679.819.896 1.381.164.422.36 1.057.413 2.227.057 1.266.07 1.646.07 4.85s-.015 3.585-.074 4.85c-.061 1.17-.256 1.805-.421 2.227-.224.562-.479.96-.899 1.382-.419.419-.824.679-1.38.896-.42.164-1.065.36-2.235.413-1.274.057-1.649.07-4.859.07-3.211 0-3.586-.015-4.859-.074-1.171-.061-1.816-.256-2.236-.421-.569-.224-.96-.479-1.379-.899-.421-.419-.69-.824-.9-1.38-.165-.42-.359-1.065-.42-2.235-.045-1.26-.061-1.649-.061-4.844 0-3.196.016-3.586.061-4.861.061-1.17.255-1.814.42-2.234.21-.57.479-.96.9-1.381.419-.419.81-.689 1.379-.898.42-.166 1.051-.361 2.221-.421 1.275-.045 1.65-.06 4.859-.06l.045.03zm0 3.678c-3.405 0-6.162 2.76-6.162 6.162 0 3.405 2.76 6.162 6.162 6.162 3.405 0 6.162-2.76 6.162-6.162 0-3.405-2.76-6.162-6.162-6.162zM12 16c-2.21 0-4-1.79-4-4s1.79-4 4-4 4 1.79 4 4-1.79 4-4 4zm7.846-10.405c0 .795-.646 1.44-1.44 1.44-.795 0-1.44-.646-1.44-1.44 0-.794.646-1.439 1.44-1.439.793-.001 1.44.645 1.44 1.439z"
              />
            </svg>

            <svg
              @click="goTo(fbUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-yellow-400 dark:hover:text-yellow-400"
              fill="currentColor"
              role="img"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
            >
              <title>Facebook icon</title>
              <path
                d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
              />
            </svg>
          </div>
        </div>
        <div class="flex w-full max-w-6xl mt-4" id="intro">
          <div
            class="flex w-full p-8 space-x-0 bg-white rounded-lg  dark:bg-gray-800 sm:p-4 sm:space-x-8"
          >
            <div class="static hidden sm:block">
              <div class="relative w-40 rounded-lg cursor-pointer group h-50">
                <img src="/photo2.png" class="w-full rounded-lg" alt="" />
                <div class="absolute top-0 left-0">
                  <img
                    src="/photo.png"
                    class="w-full transition duration-300 rounded-lg opacity-0  group-hover:opacity-100"
                    alt=""
                  />
                </div>
              </div>
            </div>

            <div
              class="flex flex-col items-center justify-between w-full  lg:flex-row"
            >
              <div
                class="flex flex-col items-center justify-center w-full h-full space-y-6  lg:w-max sm:items-start sm:space-y-3"
              >
                <h1
                  class="mt-0 text-5xl font-bold text-center text-black  dark:text-gray-50 sm:mt-0 sm:text-left"
                >
                  <span class="inline text-yellow-400">Matej </span>
                  <span class="inline text-yellow-400">Bačo </span>
                  <span class="hidden sm:inline">👋</span>
                </h1>
                <h2
                  class="mt-6 mb-4 text-2xl font-semibold text-center text-gray-400  sm:mb-0 sm:mt-0 sm:text-left"
                >
                  <span class="font-bold text-gray-900 dark:text-white"
                    >Open-minded</span
                  >
                  website developer.
                </h2>

                <!-- <p class="font-bold text-yellow-300 cursor-pointer">
              Make a payment
            </p> -->
              </div>

              <div
                class="flex flex-col items-center justify-center w-full h-full py-3 mt-6 space-y-2  lg:w-max sm:items-start lg:items-end lg:px-2 sm:mt-2"
              >
                <div
                  class="flex justify-start cursor-pointer group lg:justify-end"
                >
                  <div
                    @click="onDownloadCV()"
                    style="width: fit-content"
                    class="flex p-2 text-xl font-bold text-gray-500 transition duration-300 rounded-lg  lg:float-right dark:bg-gray-900 bg-gray-50 group-hover:bg-yellow-400 group-hover:text-white"
                  >
                    Download CV

                    <svg
                      class="w-6 h-6 ml-3 text-gray-500 transition duration-300  group-hover:text-white"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 20 20"
                      fill="currentColor"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M6 2a2 2 0 00-2 2v12a2 2 0 002 2h8a2 2 0 002-2V7.414A2 2 0 0015.414 6L12 2.586A2 2 0 0010.586 2H6zm5 6a1 1 0 10-2 0v3.586l-1.293-1.293a1 1 0 10-1.414 1.414l3 3a1 1 0 001.414 0l3-3a1 1 0 00-1.414-1.414L11 11.586V8z"
                        clip-rule="evenodd"
                      />
                    </svg>
                  </div>
                </div>

                <div
                  class="justify-start cursor-pointer  group cursor-pointerflex lg:justify-end"
                >
                  <div
                    @click="onPrintCV()"
                    style="width: fit-content"
                    class="flex p-2 text-xl font-bold text-gray-500 transition duration-300 rounded-lg  lg:float-right dark:bg-gray-900 bg-gray-50 group-hover:bg-yellow-100 group-hover:text-yellow-400"
                  >
                    Print CV

                    <svg
                      class="w-6 h-6 ml-3 text-gray-500 transition duration-300  group-hover:text-yellow-400"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 20 20"
                      fill="currentColor"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M5 4v3H4a2 2 0 00-2 2v3a2 2 0 002 2h1v2a2 2 0 002 2h6a2 2 0 002-2v-2h1a2 2 0 002-2V9a2 2 0 00-2-2h-1V4a2 2 0 00-2-2H7a2 2 0 00-2 2zm8 0H7v3h6V4zm0 8H7v4h6v-4z"
                        clip-rule="evenodd"
                      />
                    </svg>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="flex items-center justify-center">
        <div class="grid w-full max-w-6xl mt-4 gap-y-4">
          <core-portfolio-row
            :isOpened="currentlyOpened === 'skills'"
            v-on:activate="onOpenSection($event)"
            id="skills"
            colorParent="from-pink-300 to-pink-500"
            colorParent2="bg-pink-300"
            colorNameBg="bg-pink-200"
            colorNameText="text-pink-600"
            colorNameDark="text-pink-500 dark:text-pink-400"
            title="Skills Portfolio"
            iconD="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
          >
            <div class="grid w-full grid-cols-12 gap-x-0 lg:gap-x-6 gap-y-6">
              <div class="col-span-12 xl:col-span-8">
                <div class="max-w-xs">
                  <h1 class="text-xl font-bold text-black dark:text-gray-50">
                    I prepare
                    <span class="text-pink-500">modern websites</span> from the
                    first line of the code. Every website I build is using
                    <a
                      href="https://appwrite.io/"
                      target="_blank"
                      class="text-pink-500"
                    >
                      Appwrite</a
                    >
                    backend as a service.
                  </h1>
                </div>

                <div class="grid grid-cols-12 gap-6 mt-8">
                  <div
                    class="flex flex-col col-span-12 space-y-8 md:col-span-6"
                  >
                    <div
                      class="p-6 bg-gray-100 rounded-lg dark:bg-gray-900"
                      v-for="(stackItem, stackableInex) of stackItemsLeft"
                      :key="stackableInex"
                    >
                      <div
                        v-bind:class="
                          stackItem.isSpecial ? 'bg-pink-500' : 'bg-blue-400'
                        "
                        class="flex items-center justify-center w-full h-20 rounded-lg "
                        v-html="stackItem.iconSvg"
                      ></div>

                      <div class="flex flex-col w-full mt-6 space-y-4">
                        <span
                          class="text-2xl font-bold text-black  dark:text-gray-100"
                          >{{ stackItem.title }}</span
                        >

                        <span
                          class="text-lg font-semibold text-gray-600  dark:text-gray-400"
                          >{{ stackItem.text }}</span
                        >
                      </div>
                    </div>
                  </div>
                  <div
                    class="flex flex-col col-span-12 space-y-8  md:col-span-6 md:-mt-32"
                  >
                    <div
                      class="p-6 bg-gray-100 rounded-lg dark:bg-gray-900"
                      v-for="(stackItem, index) of stackItemsRight"
                      :key="index"
                    >
                      <div
                        class="flex items-center justify-center w-full h-20 bg-blue-400 rounded-lg "
                        v-html="stackItem.iconSvg"
                      ></div>

                      <div class="flex flex-col w-full mt-6 space-y-4">
                        <span
                          class="text-2xl font-bold text-black  dark:text-gray-100"
                          >{{ stackItem.title }}</span
                        >

                        <span
                          class="text-lg font-semibold text-gray-600  dark:text-gray-400"
                          >{{ stackItem.text }}</span
                        >
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div
                class="grid w-full grid-cols-12 col-span-12  xl:col-span-4 gap-y-8"
                style="height: fit-content"
              >
                <div class="col-span-12 md:col-span-6 xl:col-span-12">
                  <h1 class="text-xl font-bold text-black dark:text-gray-50">
                    Coding skills:
                  </h1>

                  <div class="flex flex-col mt-4 space-y-4">
                    <div
                      class="flex space-x-3"
                      v-for="(codingSkill, index) of codingSkills"
                      :key="index"
                    >
                      <div class="flex items-center justify-center">
                        <svg
                          v-bind:class="
                            codingSkill.level < i
                              ? ['text-gray-200', 'dark:text-gray-600']
                              : ['text-green-400']
                          "
                          v-for="i of [1, 2, 3, 4, 5]"
                          :key="i"
                          class="w-6 h-6"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                          fill="currentColor"
                        >
                          <path
                            d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
                          />
                        </svg>
                      </div>
                      <span
                        class="text-xl font-bold text-gray-600  dark:text-gray-300"
                      >
                        {{ codingSkill.name }}
                      </span>
                    </div>
                  </div>
                </div>

                <div class="col-span-12 md:col-span-6 xl:col-span-12">
                  <h1 class="text-xl font-bold text-black dark:text-gray-50">
                    Technologies:
                  </h1>

                  <div class="flex flex-col mt-4 space-y-4">
                    <div
                      class="flex space-x-3"
                      v-for="(technologiesSkill, index) of technologiesSkills"
                      :key="index"
                    >
                      <div class="flex items-center justify-center">
                        <svg
                          v-bind:class="
                            technologiesSkill.level < i
                              ? ['text-gray-200', 'dark:text-gray-600']
                              : ['text-pink-500']
                          "
                          v-for="i of [1, 2, 3, 4, 5]"
                          :key="i"
                          class="w-6 h-6"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                          fill="currentColor"
                        >
                          <path
                            fill-rule="evenodd"
                            d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z"
                            clip-rule="evenodd"
                          />
                        </svg>
                      </div>
                      <span
                        class="text-xl font-bold text-gray-600  dark:text-gray-300"
                      >
                        {{ technologiesSkill.name }}
                      </span>
                    </div>
                  </div>
                </div>

                <div class="col-span-12 md:col-span-6 xl:col-span-12">
                  <h1 class="text-xl font-bold text-black dark:text-gray-50">
                    Language skills:
                  </h1>

                  <div class="flex flex-col mt-4 space-y-4">
                    <div
                      class="flex space-x-3"
                      v-for="(langSkill, index) of langSkills"
                      :key="index"
                    >
                      <div class="flex items-center justify-center">
                        <svg
                          v-bind:class="
                            langSkill.level < i
                              ? ['text-gray-200', 'dark:text-gray-600']
                              : ['text-yellow-400']
                          "
                          v-for="i of [1, 2, 3, 4, 5]"
                          :key="i"
                          class="w-6 h-6"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                          fill="currentColor"
                        >
                          <path
                            fill-rule="evenodd"
                            d="M11.3 1.046A1 1 0 0112 2v5h4a1 1 0 01.82 1.573l-7 10A1 1 0 018 18v-5H4a1 1 0 01-.82-1.573l7-10a1 1 0 011.12-.38z"
                            clip-rule="evenodd"
                          />
                        </svg>
                      </div>
                      <span
                        class="text-xl font-bold text-gray-600  dark:text-gray-300"
                      >
                        {{ langSkill.name }}
                      </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </core-portfolio-row>

          <core-portfolio-row
            :isOpened="currentlyOpened === 'projects'"
            v-on:activate="onOpenSection($event)"
            id="projects"
            colorParent="from-green-300 to-green-500"
            colorParent2="bg-green-300"
            colorNameBg="bg-green-200"
            colorNameText="text-green-600"
            colorNameDark="text-green-500 dark:text-green-400"
            title="Successful Projects"
            iconD="M17 8h2a2 2 0 012 2v6a2 2 0 01-2 2h-2v4l-4-4H9a1.994 1.994 0 01-1.414-.586m0 0L11 14h4a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2v4l.586-.586z"
          >
            <h1 class="text-xl font-bold text-black dark:text-gray-50">
              With more than
              <span class="text-green-400">20 finished projects</span> over one
              year of frelanding, I am a strong developer ready to bring my
              skill set into every project.
            </h1>

            <div class="grid grid-cols-12 gap-6 mt-8">
              <div
                v-for="(project, i) of projects"
                :key="i"
                v-bind:class="project.grid"
                class="relative p-2 bg-green-400 rounded-lg cursor-pointer  group h-80"
                @click="onOpenGallery(i)"
              >
                <div
                  class="w-full h-full rounded-lg"
                  v-bind:style="{
                    backgroundImage: 'url(\'' + project.mainImage + '\')',
                  }"
                  style="background-size: cover; background-position: center"
                ></div>

                <div
                  style="background-color: rgba(0, 0, 0, 0.7)"
                  class="absolute inset-0 flex flex-col items-center justify-center p-6 transition duration-300 rounded-lg opacity-0  group-hover:opacity-100"
                >
                  <h3 class="text-2xl font-bold text-center text-white">
                    {{ project.name }}
                  </h3>
                  <p
                    class="mt-3 font-semibold text-center text-gray-100 text-md"
                  >
                    {{ project.description }}
                  </p>
                </div>
              </div>
            </div>
          </core-portfolio-row>

          <core-portfolio-row
            :isOpened="currentlyOpened === 'reviews'"
            v-on:activate="onOpenSection($event)"
            id="reviews"
            colorParent="from-indigo-300 to-indigo-500"
            colorParent2="bg-indigo-300"
            colorNameBg="bg-indigo-200"
            colorNameText="text-indigo-600"
            colorNameDark="text-indigo-500 dark:text-indigo-400"
            title="Client Reviews"
            iconD="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z"
          >
            <h1 class="text-xl font-bold text-black dark:text-gray-50">
              Here's what some <span class="text-indigo-400">companies</span> I
              worked with as freelancer have to say about my work.
            </h1>

            <div class="flex flex-col mt-8 space-y-16 sm:space-y-8">
              <div
                class="flex flex-col items-center justify-center space-x-0  sm:space-x-8 sm:flex-row sm:items-start sm:justify-start"
                v-for="(review, index) of reviews"
                :key="index"
              >
                <img :src="review.image" class="w-40 rounded-lg" alt="" />
                <div>
                  <h1
                    class="mt-6 text-3xl font-bold text-center text-black  dark:text-gray-50 sm:mt-0 sm:text-left"
                  >
                    {{ review.name }}
                  </h1>
                  <h3
                    class="text-xl font-bold text-center text-indigo-400  sm:text-left"
                  >
                    {{ review.company }}
                  </h3>

                  <div
                    class="hidden w-40 h-1 mt-2 bg-gray-200 rounded-full  sm:block dark:bg-gray-700"
                  ></div>

                  <p
                    class="mt-2 text-lg font-semibold text-center sm:text-left"
                  >
                    {{ review.text }}
                  </p>
                </div>
              </div>
            </div>
          </core-portfolio-row>

          <core-portfolio-row
            :isOpened="currentlyOpened === 'contact'"
            v-on:activate="onOpenSection($event)"
            id="contact"
            colorParent="from-red-300 to-red-500"
            colorParent2="bg-red-300"
            colorNameBg="bg-red-200"
            colorNameText="text-red-600"
            colorNameDark="text-red-500 dark:text-red-400"
            title="Contact me"
            iconD="M17 8h2a2 2 0 012 2v6a2 2 0 01-2 2h-2v4l-4-4H9a1.994 1.994 0 01-1.414-.586m0 0L11 14h4a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2v4l.586-.586z"
          >
            <h1 class="text-xl font-bold text-black dark:text-gray-50">
              Contact me if you have any questions. I will be more than happy to
              get in touch with you.
            </h1>
            <p class="mt-6 font-bold text-gray-500 dark:text-gray-500">
              <span class="mr-1">E-mail:</span>
              <a
                :href="'mailto:' + contactEmail"
                class="text-red-400 cursor-pointer"
              >
                {{ contactEmail }}
              </a>
            </p>
            <p class="mt-2 font-bold text-gray-500 dark:text-gray-500">
              <span class="mr-1">Phone number:</span>
              <a
                :href="'tel:' + contactTelPlain"
                class="text-red-400 cursor-pointer"
              >
                {{ constactTel }}
              </a>
            </p>

            <h1 class="mt-6 text-xl font-bold text-black dark:text-gray-50">
              One quick form stands between
              <span class="text-red-400">you</span> and
              <span class="text-red-400">me</span>.
            </h1>

            <form
              :action="'https://formspree.io/f/' + formSpreeKey"
              method="POST"
              class="grid grid-cols-12 gap-6 mt-6"
            >
              <input
                required=""
                class="col-span-12 p-6 font-bold bg-transparent border-4 border-gray-200  dark:border-gray-600 rounded-xl md:col-span-6 focus:outline-none focus:ring-0 focus:border-red-400"
                placeholder="Your name"
                type="text"
                name="name"
              />

              <input
                required=""
                class="col-span-12 p-6 font-bold bg-transparent border-4 border-gray-200  dark:border-gray-600 rounded-xl md:col-span-6 focus:outline-none focus:ring-0 focus:border-red-400"
                placeholder="Your e-mail"
                type="email"
                name="email"
              />

              <textarea
                required=""
                style="resize: none"
                class="col-span-12 p-6 font-bold bg-transparent border-4 border-gray-200  dark:border-gray-600 rounded-xl md:col-span-12 focus:outline-none focus:ring-0 focus:border-red-400"
                placeholder="Your message"
                rows="10"
                name="message"
              ></textarea>

              <div class="hidden col-span-6 md:block"></div>

              <button
                type="submit"
                class="col-span-12 p-6 text-xl font-bold text-white bg-red-400 rounded-lg  md:col-span-6 hover:bg-red-500"
              >
                Submit
              </button>
            </form>
          </core-portfolio-row>
        </div>
      </div>

      <div class="flex items-center justify-center">
        <div
          class="w-full max-w-6xl mt-4 font-bold text-center text-gray-500  dark:text-gray-500"
        >
          v1.0.0 &copy; {{ currentYear }}, Matej Bačo. All Rights Reserved.
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

declare const PhotoSwipeUI_Default: any
declare const PhotoSwipe: any

export default Vue.extend({
  data() {
    return {
      isDark: true,

      formSpreeKey: 'xrgjpobb',
      fbUrl: 'https://www.facebook.com/matejbaco2000',
      messengerUrl: 'https://m.me/102386341636067',
      gitHubUrl: 'https://github.com/meldiron',
      discordUrl: 'https://discordapp.com/channels/@me/287294735054274560/',
      whatsappUrl: 'https://wa.me/421919178798',
      igUrl: 'https://www.instagram.com/matejbaco2000/',

      contactEmail: 'matejbaco2000@gmail.com',
      constactTel: '+421 919 178 798',
      contactTelPlain: '+421919178798',

      codingSkills: [
        {
          name: 'Typescript',
          level: 5,
        },
        {
          name: 'PHP',
          level: 4,
        },
        {
          name: 'MySQL',
          level: 4,
        },
        {
          name: 'CSS',
          level: 4,
        },
        {
          name: 'HTML',
          level: 4,
        },
      ],

      technologiesSkills: [
        {
          name: 'Appwrite',
          level: 5,
        },
        {
          name: 'Git',
          level: 4,
        },
        {
          name: 'Docker',
          level: 4,
        },
        {
          name: 'Regex',
          level: 4,
        },
        {
          name: 'Markdown',
          level: 4,
        },
        {
          name: 'PM2',
          level: 3,
        },
        {
          name: 'Nginx',
          level: 3,
        },
        {
          name: 'Linux',
          level: 3,
        },
      ],

      stackItemsLeft: [
        {
          isSpecial: true,
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Appwrite</title><path d="M7.834 4C4.094 4.09.584 6.816.06 11.014a7.993 7.994 0 0 0 3.122 7.368c2.757 2.08 6.198 2.047 8.82.538a7.993 7.994 0 1 0-.005-13.834A7.84 7.84 0 0 0 7.831 4zm.122 1.485a6.525 6.526 0 0 1 6.484 5.537c0 .007.002.013.003.02.02.143.037.287.048.433l.006.054c.01.15.016.303.017.456 0 .084-.005.168-.008.252-.002.058-.003.117-.007.175a6.68 6.68 0 0 1-.03.335l-.01.08c-.015.12-.033.24-.055.358l-.01.048c-.022.124-.05.248-.08.37l-.006.025a6.578 6.58 0 0 1-.41 1.15c-.007.016-.017.033-.024.05a6.538 6.54 0 0 1-1.62 2.115l-.054.046c-.08.067-.162.13-.245.194-.055.042-.11.084-.168.125-.04.03-.08.056-.122.084a6.68 6.68 0 0 1-1.123.612 6.517 6.518 0 0 1-6.468-.8C.069 14.184.838 7.96 5.457 6.004a6.512 6.513 0 0 1 2.499-.518zm.61 3.72c-.183 0-.343.013-.352.032-.01.024-.132.504-.264 1.074-.136.57-.353 1.468-.475 2-.235.974-.377 1.613-.377 1.698 0 .023.146.042.325.042h.325l.146-.65.423-1.796c.15-.635.334-1.408.405-1.72.07-.31.14-.591.155-.624.014-.043-.066-.057-.31-.057zm-2.441 1.6-.438.47-.433.47.127.15c.07.086.264.298.428.472l.302.32h.856l-.405-.438c-.221-.235-.405-.46-.405-.49 0-.032.17-.243.377-.47.207-.23.376-.428.376-.45 0-.02-.178-.034-.395-.034zm3.27 0c-.231 0-.415.014-.415.028s.08.103.18.202c.366.367.624.678.61.74-.009.032-.188.253-.405.484l-.39.428h.437l.438-.005.4-.438c.22-.244.4-.46.4-.49 0-.023-.188-.244-.424-.493l-.423-.457z"/></svg>`,
          title: 'Appwrite',
          text: `Appwrite is extendable set of tools for developer to rapidly prepare reliable, secure, and scalable solutions.`,
        },
        {
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Vue.js</title><path d="M24,1.61H14.06L12,5.16,9.94,1.61H0L12,22.39ZM12,14.08,5.16,2.23H9.59L12,6.41l2.41-4.18h4.43Z"/></svg>`,
          title: 'Vue.js',
          text: `Vue is a development framework for creating efficient and sophisticated single-page applications.`,
        },
        {
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Tailwind CSS icon</title><path d="M12.001,4.8c-3.2,0-5.2,1.6-6,4.8c1.2-1.6,2.6-2.2,4.2-1.8c0.913,0.228,1.565,0.89,2.288,1.624 C13.666,10.618,15.027,12,18.001,12c3.2,0,5.2-1.6,6-4.8c-1.2,1.6-2.6,2.2-4.2,1.8c-0.913-0.228-1.565-0.89-2.288-1.624 C16.337,6.182,14.976,4.8,12.001,4.8z M6.001,12c-3.2,0-5.2,1.6-6,4.8c1.2-1.6,2.6-2.2,4.2-1.8c0.913,0.228,1.565,0.89,2.288,1.624 c1.177,1.194,2.538,2.576,5.512,2.576c3.2,0,5.2-1.6,6-4.8c-1.2,1.6-2.6,2.2-4.2,1.8c-0.913-0.228-1.565-0.89-2.288-1.624 C10.337,13.382,8.976,12,6.001,12z"/></svg>`,
          title: 'Tailwind',
          text: `Tailwind is a desining framework that can be used to rapidly design and build modern websites.`,
        },
      ],

      stackItemsRight: [
        {
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Vercel</title><path d="M24 22.525H0l12-21.05 12 21.05z"/></svg>`,
          title: 'Vercel',
          text: `Vercel let's your application go live! Vercel lets you host a website and bring content to visitors all around the world.`,
        },
        {
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Stripe</title><path d="M13.976 9.15c-2.172-.806-3.356-1.426-3.356-2.409 0-.831.683-1.305 1.901-1.305 2.227 0 4.515.858 6.09 1.631l.89-5.494C18.252.975 15.697 0 12.165 0 9.667 0 7.589.654 6.104 1.872 4.56 3.147 3.757 4.992 3.757 7.218c0 4.039 2.467 5.76 6.476 7.219 2.585.92 3.445 1.574 3.445 2.583 0 .98-.84 1.545-2.354 1.545-1.875 0-4.965-.921-6.99-2.109l-.9 5.555C5.175 22.99 8.385 24 11.714 24c2.641 0 4.843-.624 6.328-1.813 1.664-1.305 2.525-3.236 2.525-5.732 0-4.128-2.524-5.851-6.594-7.305h.003z"/></svg>`,
          title: 'Stripe',
          text: `Stripe is the easiest way to start collecting payments from your customers from all over the world. Both one-time payments and subscriptions can be easily implemented.`,
        },
        {
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>TransferWise icon</title><path d="M9.871 24h3.11L23.127 0H3.694l3.748 6.291-6.571 6.283h11.361l1.068-2.517H7.03l3.792-3.783L8.61 2.516h10.337z"/></svg>`,
          title: 'Localization (i18n)',
          text: `i18n is a lightweight simple internationalization framework that lets connect developers and translators to create multilingual websites.`,
        },
      ],

      langSkills: [
        {
          name: `Slovak`,
          level: 5,
        },
        {
          name: `Czech`,
          level: 4,
        },
        {
          name: `English`,
          level: 3,
        },
      ],

      reviews: [
        {
          name: "Branislav 'Čivo' Kovačovic",
          company: `Topgaming.eu CEO`,
          image: '/clients/civo.jpg',
          text: `Cooperation with Matej was without the slightest complications. Solution Matej prepared for us made our website really unique.`,
        },

        {
          name: 'Denis Sedlák',
          company: `Hiroo.eu CEO`,
          image: '/clients/denis.jpg',
          text: `Cooperation with Matej was very professional, punctual and with a high-quality level. He is not only coder but also business thinker and I am sure you will be satisfied with his work.`,
        },

        {
          name: "David 'Kellwiin' Helikar",
          company: `Twitch.tv content creator`,
          image: '/clients/kellwiin.png',
          text: `Well done job in short peroid of time. Interaction with client was wihout any problem, developer was able to satisfy all my needs. I am really happy about active updates he is able to do. I would love to use your services again in future.`,
        },

        {
          name: "Pablo 'Hyper' Sanchez",
          company: `RealmsMP Owner`,
          image: '/clients/hyper.png',
          text: `Matej is my go to dev. He is very informative and helpful when it comes to explaining what he is doing and why. I appreciate how thorough and diligent he is with his code and work in general. He has coded many plugins for me and I do not like working with anybody else, specially after having been spoiled by his great work.  Matej works hard and tracks all his hours worked very carefully. He constantly updates me throughout the day. I would highly recommend his services to anybody looking for any type of coding work/projects.`,
        },
        {
          name: 'Neiz',
          company: `EGM Admin team leader`,
          image: '/clients/egm.png',
          text: `Very good, fast, and professional service. Quick responses and great patience lead to an awesome experience.`,
        },
        {
          name: 'Wake',
          company: `CraftMania.cz Owner`,
          image: '/clients/cm.png',
          text: `Overall, great job! Plugins are well made and I must say, Matej is really good with GUI menus in Minecraft development.`,
        },
      ],

      projects: [
        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-12'],
          mainImage: '/projects/hiroo/hiroo1.png',
          name: 'Hiroo',
          description: `Online candidate pre-selection SaaS.`,
          images: [
            '/projects/hiroo/hiroo1.png',
            '/projects/hiroo/hiroo2.png',
            '/projects/hiroo/hiroo3.png',
            '/projects/hiroo/hiroo4.png',
            '/projects/hiroo/hiroo5.png',
            '/projects/hiroo/hiroo6.png',
            '/projects/hiroo/hiroo7.png',
            '/projects/hiroo/hiroo8.png',
            '/projects/hiroo/hiroo9.png',
          ],
        },

        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-4'],
          mainImage: '/projects/dreamland/dreamland1.png',
          name: 'Dream Land',
          description: `Minecraft server website presentation.`,
          images: ['/projects/dreamland/dreamland1.png'],
        },

        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-8'],
          mainImage: '/projects/adamko/adamko1.png',
          name: 'Adamko',
          description: `Professional portfolio for a Twitch content creator.`,
          images: [
            '/projects/adamko/adamko1.png',
            '/projects/adamko/adamko2.png',
            '/projects/adamko/adamko3.png',
            '/projects/adamko/adamko4.png',
            '/projects/adamko/adamko5.png',
            '/projects/adamko/adamko6.png',
            '/projects/adamko/adamko7.png',
            '/projects/adamko/adamko8.png',
          ],
        },

        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-8'],
          mainImage: '/projects/unicraft/unicraft1.png',
          name: 'Uni-Craft World',
          description: `Minecraft server website presentation.`,
          images: [
            '/projects/unicraft/unicraft1.png',
            '/projects/unicraft/unicraft2.png',
          ],
        },
        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-4'],
          mainImage: '/projects/rensk/rensk1.png',
          name: 'REN Slovakia',
          description: `E-commerce solution for a Slovakia startup.`,
          images: [
            '/projects/rensk/rensk1.png',
            '/projects/rensk/rensk2.png',
            '/projects/rensk/rensk3.png',
            '/projects/rensk/rensk4.png',
            '/projects/rensk/rensk5.png',
            '/projects/rensk/rensk6.png',
            '/projects/rensk/rensk7.png',
            '/projects/rensk/rensk8.png',
            '/projects/rensk/rensk9.png',
            '/projects/rensk/rensk10.png',
          ],
        },
        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-4'],
          mainImage: '/projects/codeink/codeink1.png',
          name: 'Code Ink',
          description: `Presentation website for a software studio.`,
          images: [
            '/projects/codeink/codeink1.png',
            '/projects/codeink/codeink2.png',
            '/projects/codeink/codeink3.png',
            '/projects/codeink/codeink4.png',
            '/projects/codeink/codeink5.png',
            '/projects/codeink/codeink6.png',
            '/projects/codeink/codeink7.png',
            '/projects/codeink/codeink8.png',
            '/projects/codeink/codeink9.png',
            '/projects/codeink/codeink10.png',
            '/projects/codeink/codeink11.png',
            '/projects/codeink/codeink12.png',
            '/projects/codeink/codeink13.png',
            '/projects/codeink/codeink14.png',
            '/projects/codeink/codeink15.png',
            '/projects/codeink/codeink16.png',
          ],
        },
        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-4'],
          mainImage: '/projects/gallamini/galla1.png',
          name: 'Gallactic Mini',
          description: `Presentation website for a Minecraft server.`,
          images: [
            '/projects/gallamini/galla1.png',
            '/projects/gallamini/galla2.png',
            '/projects/gallamini/galla3.png',
            '/projects/gallamini/galla4.png',
            '/projects/gallamini/galla5.png',
            '/projects/gallamini/galla6.png',
            '/projects/gallamini/galla7.png',
            '/projects/gallamini/galla8.png',
            '/projects/gallamini/galla9.png',
            '/projects/gallamini/galla10.png',
            '/projects/gallamini/galla11.png',
            '/projects/gallamini/galla12.png',
            '/projects/gallamini/galla13.png',
            '/projects/gallamini/galla14.png',
            '/projects/gallamini/galla15.png',
          ],
        },
        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-4'],
          mainImage: '/projects/kblog/kblog1.png',
          name: 'Kellwiin Blog',
          description: `Personalized blog solution for a content creator.`,
          images: [
            '/projects/kblog/kblog1.png',
            '/projects/kblog/kblog2.png',
            '/projects/kblog/kblog3.png',
            '/projects/kblog/kblog4.png',
            '/projects/kblog/kblog5.png',
          ],
        },

        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-12'],
          mainImage: '/projects/kellwiin/kellwiin1.png',
          name: 'Kellwiin',
          description: `Professional portfolio for a Twitch content creator.`,
          images: [
            '/projects/kellwiin/kellwiin1.png',
            '/projects/kellwiin/kellwiin2.png',
            '/projects/kellwiin/kellwiin3.png',
            '/projects/kellwiin/kellwiin4.png',
            '/projects/kellwiin/kellwiin5.png',
            '/projects/kellwiin/kellwiin6.png',
            '/projects/kellwiin/kellwiin7.png',
            '/projects/kellwiin/kellwiin8.png',
            '/projects/kellwiin/kellwiin9.png',
            '/projects/kellwiin/kellwiin10.png',
            '/projects/kellwiin/kellwiin11.png',
          ],
        },

        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-4'],
          mainImage: '/projects/kbody/kbody1.png',
          name: 'Kellwiin Event',
          description: `Database solution for an in-game event analytics including results interface.`,
          images: [
            '/projects/kbody/kbody1.png',
            '/projects/kbody/kbody2.png',
            '/projects/kbody/kbody3.png',
            '/projects/kbody/kbody4.png',
          ],
        },

        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-8'],
          mainImage: '/projects/matejbaco/matejbaco1.png',
          name: 'Matej Bačo',
          description: `My own old presentation website.`,
          images: [
            '/projects/matejbaco/matejbaco1.png',
            '/projects/matejbaco/matejbaco2.png',
            '/projects/matejbaco/matejbaco3.png',
            '/projects/matejbaco/matejbaco4.png',
            '/projects/matejbaco/matejbaco5.png',
            '/projects/matejbaco/matejbaco6.png',
            '/projects/matejbaco/matejbaco7.png',
            '/projects/matejbaco/matejbaco8.png',
            '/projects/matejbaco/matejbaco9.png',
            '/projects/matejbaco/matejbaco10.png',
            '/projects/matejbaco/matejbaco11.png',
            '/projects/matejbaco/matejbaco12.png',
          ],
        },
        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-8'],
          mainImage: '/projects/tuke/tuke1.png',
          name: 'TUKE Website',
          description: `University website to serve studying materials.`,
          images: [
            '/projects/tuke/tuke1.png',
            '/projects/tuke/tuke2.png',
            '/projects/tuke/tuke3.png',
            '/projects/tuke/tuke4.png',
            '/projects/tuke/tuke5.png',
            '/projects/tuke/tuke6.png',
            '/projects/tuke/tuke7.png',
            '/projects/tuke/tuke8.png',
            '/projects/tuke/tuke9.png',
          ],
        },

        {
          grid: ['col-span-12 md:col-span-12 lg:col-span-4'], // TODO: Ked pridavas, pozor aby to bolo pekne zakonecne aj na MD aj na LG
          mainImage: '/projects/mboros/boros1.png',
          name: 'Michael Boroš',
          description: `Presentation website for photographer.`,
          images: [
            '/projects/mboros/boros1.png',
            '/projects/mboros/boros2.png',
            '/projects/mboros/boros3.png',
            '/projects/mboros/boros4.png',
            '/projects/mboros/boros5.png',
            '/projects/mboros/boros6.png',
          ],
        },
      ],

      currentlyOpened: 'none',
      iframe: null as any,
      currentYear: new Date().getFullYear(),

      currentColor: 'from-yellow-300 to-yellow-500',
      // from-{{ currentColor }}-300 to-{{ currentColor }}-500

      currentColor2: 'bg-yellow-300',
      // bg-{{ currentColor }}-300
    }
  },
  methods: {
    onToggleDar() {
      this.isDark = !this.isDark
      this.syncDarkness()
    },
    onDownloadCV() {
      const link = document.createElement('a')
      link.download = 'CV_Matej_Baco.pdf'
      link.href = '/CV_Matej_Baco.pdf'

      document.body.appendChild(link)
      link.click()

      document.body.removeChild(link)
    },

    onPrintCV() {
      if (this.iframe) {
        if (this.iframe.contentWindow) {
          this.iframe.focus()
          this.iframe.contentWindow.print()
        }
        return
      }

      this.iframe = document.createElement('iframe')
      document.body.appendChild(this.iframe)

      this.iframe.style.display = 'none'
      this.iframe.onload = () => {
        setTimeout(() => {
          if (this.iframe.contentWindow) {
            this.iframe.focus()
            this.iframe.contentWindow.print()
          }
        }, 300)
      }

      this.iframe.src = '/CV_Matej_Baco.pdf'
    },

    goTo(url: string) {
      window.location.href = url
    },

    scroll(el: any) {
      const dateStart = Date.now()

      let i = 0
      const step = (wrapper: any, i: number) => {
        if (i > 60 || Math.abs(dateStart - Date.now()) > 600) {
          return
        }

        const destinationPos = el.offsetTop - 15
        const currentPos = wrapper.scrollTop

        let stepLength = Math.max(
          20,
          Math.abs(currentPos - destinationPos) * 0.2
        )

        if (Math.abs(currentPos - destinationPos) < 500) {
          stepLength = 20
        }

        let newPos
        if (currentPos > destinationPos) {
          newPos = currentPos - stepLength

          if (newPos < destinationPos) {
            newPos = destinationPos
          }
        } else {
          newPos = currentPos + stepLength

          if (newPos > destinationPos) {
            newPos = destinationPos
          }
        }

        wrapper.scrollTo(null, newPos)

        setTimeout(() => {
          step(wrapper, i + 1)
        }, 10)
      }

      const wrapper: any = document.querySelector('#page_wrapper')
      if (el && wrapper) {
        step(wrapper, 0)
      }
    },

    checkVisible(elm: any) {
      return false
      // var rect = elm.getBoundingClientRect();
      // var viewHeight = Math.max(
      //   document.documentElement.clientHeight,
      //   window.innerHeight
      // );
      // return !(rect.bottom < 0 || rect.top - viewHeight >= 0);
    },

    onOpenSection(event: { color: string; color2: string; id: string }) {
      if (this.currentlyOpened === event.id) {
        this.currentlyOpened = 'none'
        this.currentColor = 'from-yellow-300 to-yellow-500'
        this.currentColor2 = 'bg-yellow-300'

        const selector: any = document.querySelector('#intro')
        // this.scroll(selector)

        return
      }

      this.currentColor = event.color
      this.currentColor2 = event.color2
      this.currentlyOpened = event.id

      const selector: any = document.querySelector('#' + event.id)
      // this.scroll(selector)
    },

    onOpenGallery(projectIndex: number) {
      const project = this.projects[projectIndex]
      const pswpElement = document.querySelector('.pswp')

      const items = project.images.map((img) => {
        return {
          src: img,
          w: 1920,
          h: 1200,
        }
      })
      console.log(items)

      const options = {
        index: 0,
      }

      const gallery = new PhotoSwipe(
        pswpElement,
        PhotoSwipeUI_Default,
        items,
        options
      )
      gallery.init()
    },
    syncDarkness() {
      if (this.isDark) {
        document.body.classList.add('dark')
      } else {
        document.body.classList.remove('dark')
      }
    },
  },
  created() {
    this.syncDarkness()
  },
})
</script>
