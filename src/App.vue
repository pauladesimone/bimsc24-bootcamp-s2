<!-- // Script is in some way equivalent to script.js. This is a place
to define variables, methods, and imports of other Vue components. -->
<script setup>
// imports reference from vue library
import { ref } from "vue";

// Define variables and constants
let name = ref("Paula");

// Array of coding-related poems
let poems = [
  { title: "The Symphony of Code", content: "In lines of code, a symphony plays,\nCreating systems in countless ways.\nLogic and syntax in rhythmic grace,\nA coder's world, a vast embrace." },
  { title: "Ode to the Debugger", content: "Oh, debugger, my steadfast guide,\nIn error messages, you confide.\nThrough loops and branches, side by side,\nYou unveil the bugs, nowhere to hide." },
  { title: "Code's Canvas", content: "Code, a canvas of pixels and bytes,\nCrafting worlds in digital heights.\nVariables dance in binary ballets,\nIn the realm of logic, where brilliance dwells." },
  { title: "The Algorithm's Tale", content: "Algorithms weave a tale,\nOf efficiency, they never fail.\nSorting, searching, a quest unveiled,\nIn the algorithm's world, where secrets are hailed." },
  { title: "In the Realm of Functions", content: "In the realm of functions, echoes resound,\nParameters and returns, a cycle profound.\nRecursion whispers, loops astound,\nIn the language of functions, solutions are found." },
  { title: "Binary Serenade", content: "Ones and zeros, a binary song,\nIn the language of machines, they belong.\nBytes and bits, a melody strong,\nIn the symphony of data, where memories throng." },
  { title: "Code Poetry", content: "Code, a language poetic and clear,\nStructured verses that engineers revere.\nIndentations whisper, no room for fear,\nIn the world of coding, where brilliance is near." },
  { title: "The Art of Git", content: "In branches and merges, Git unfolds,\nA versioned history, a story told.\nCommits as brushstrokes, colors bold,\nIn the art of collaboration, stories are scrolled." },
  { title: "The Enchanting API", content: "API, the enchanting spell,\nConnecting realms, where data swell.\nEndpoints beckon, a magical well,\nIn the world of integration, stories to tell." },
  { title: "Code's Elegance", content: "Elegance in code, a beauty refined,\nReadable, maintainable, a design aligned.\nPatterns and principles, in harmony bind,\nIn the realm of coding, where elegance shines." },
];

let showPoem = ref(false);
let currentPoemIndex = ref(0);

// Define functions
function displayPoem() {
  showPoem.value = true;
  // Increment index to display the next poem
  currentPoemIndex.value = (currentPoemIndex.value + 1) % poems.length;
}
</script>

<!-- Template is an HTML-based syntax that allows you to bind the rendered DOM elements
with data, objects, functions, etc. -->
<template>
  <div id="top-bar">
    <div id="title-container">
      <img class="logo-image" alt="Iaac logo" src="./assets/iaac-white.png" />
      <h2>The Poem machine by {{ name }} </h2>
    </div>
  </div>

  <div id="content">
    <!-- Button for the poem -->
    <button @click="displayPoem">Recite me a <strong>Poem</strong></button>

    <!-- Display the poem -->
    <div v-if="showPoem" class="poem-container">
      <h3>{{ poems[currentPoemIndex].title }}</h3>
      <p>{{ poems[currentPoemIndex].content }}</p>
    </div>
  </div>
</template>

<!-- Style is for CSS styling -->
<style>
  
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #922573;
}

#top-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: rgba(255, 41, 219, 0.7);
}

#title-container {
  display: flex;
  align-items: center;
  color: white;
  margin-right: 1.5rem;
}

#content {
  display: flex;
  flex-direction: column; /* Display content in a column layout */
  align-items: center; /* Center content horizontally */
  padding: 20px;
}

.logo-image {
  height: 3.25rem;
  padding: 0.5rem;
}

h2 {
  font-size: 1.125rem;
  font-weight: 600;
  letter-spacing: -0.05em;
}

.poem-container {
  margin-top: 20px;
  border: 1px solid #ccc;
  padding: 10px;
}
</style>
