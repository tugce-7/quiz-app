<template>
    <!-- quiz container -->
    <div class="overflow-hidden bg-white flex-none container relative shadow-lg rounded-lg px-12 py-6">
      <img
        src="@/assets/images/abstract.jpg"
        alt=""
        class="absolute -top-20 left-0 object-none"
      />

      <!-- contents -->
      <div class="relative z-20">
        <!-- score container -->
        <div class="text-right text-gray-800">
          <p class="text-sm leading-3">Score</p>
          <p class="font-bold">10</p>
        </div>

        <!-- question container -->
        <div
          class="rounded-lg bg-gray-100 p-2 neumorph-1 text-center font-bold text-gray-800 mt-8"
        >
          <div class="bg-white p-5">
            Javascript hangi HTML etiketi içerisinde yer alır?
          </div>
        </div>

        <!-- options container -->

        <div class="mt-8">
          <!-- option container -->
          <div
            class="neumorph-1 option-default bg-gray-100 p-2 rounded-lg mb-3 relative"
          >
            <div
              class="bg-blue-700 p-1 transform rotate-45 rounded-md h-10 w-10 text-white font-bold absolute right-0 top-0 shadow-md"
            >
              <p class="transform -rotate-45">+10</p>
            </div>
            <div class="rounded-lg font-bold flex p-2">
              <!-- option ID -->
              <div class="p-3 rounded-lg">A</div>

              <!-- option name -->
              <div class="flex items-center pl-6">js</div>
            </div>
          </div>
          <!-- correct option container -->
          <div
            class="neumorph-1 option-correct bg-gray-100 p-2 rounded-lg mb-3 relative"
          >
            <div
              class="bg-blue-700 p-1 transform rotate-45 rounded-md h-10 w-10 text-white font-bold absolute right-0 top-0 shadow-md"
            >
              <p class="transform -rotate-45">+10</p>
            </div>
            <div class="rounded-lg font-bold flex p-2">
              <!-- option ID -->
              <div class="p-3 rounded-lg">B</div>

              <!-- option name -->
              <div class="flex items-center pl-6">script</div>
            </div>
          </div>
           <!-- option container -->
          <div
            class="neumorph-1 option-default bg-gray-100 p-2 rounded-lg mb-3 relative"
          >
            <div
              class="bg-blue-700 p-1 transform rotate-45 rounded-md h-10 w-10 text-white font-bold absolute right-0 top-0 shadow-md"
            >
              <p class="transform -rotate-45">+10</p>
            </div>
            <div class="rounded-lg font-bold flex p-2">
              <!-- option ID -->
              <div class="p-3 rounded-lg">C</div>

              <!-- option name -->
              <div class="flex items-center pl-6">scripting</div>
            </div>
          </div>
           <!-- option container -->
          <div
            class="neumorph-1 option-default bg-gray-100 p-2 rounded-lg mb-3 relative"
          >
            <div
              class="bg-blue-700 p-1 transform rotate-45 rounded-md h-10 w-10 text-white font-bold absolute right-0 top-0 shadow-md"
            >
              <p class="transform -rotate-45">+10</p>
            </div>
            <div class="rounded-lg font-bold flex p-2">
              <!-- option ID -->
              <div class="p-3 rounded-lg">D</div>

              <!-- option name -->
              <div class="flex items-center pl-6">javascript</div>
            </div>
          </div>
        </div>

        <!-- progress indicator container -->
        <div class="mt-8 text-center">
          <div class="h-1 w-12 bg-gray-800 rounded-full mx-auto"></div>
          <p class="font-bold text-gray-800">1/10</p>
        </div>
      </div>
    </div>
</template>
