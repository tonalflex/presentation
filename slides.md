---
theme: default
background: black

title: Tonalflex

info: |
  # Introduction to the Tonalflex DSP app bundle.

class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
---

<img src="/logo.svg" alt="Tonalflex Logo" style="max-width: 500px; margin: auto;" />

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/tonalflex" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

---

<h1>DAW (Digital Audio Workstation)</h1>

<div class="grid grid-cols-[auto_min-content_auto] items-center gap-6 mt-16">

  <div class="h-[300px] overflow-hidden flex items-center justify-center">
    <img src="/tape.jpg" alt="Tape" class="rounded-xl h-full w-auto object-cover" />
  </div>

  <div class="text-center text-4xl text-green-500">
    →
  </div>

  <div class="h-[300px] overflow-hidden flex items-center justify-center">
    <img src="/daw.jpeg" alt="DAW" class="rounded-xl h-full w-auto object-cover" />
  </div>

</div>

<style>
h1 {
  background-image: linear-gradient(45deg, rgb(60, 122, 77) 10%, rgb(63, 167, 86) 20%);
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

<h1>Audio DSP Plugins (Demo)</h1>
<img src="/delay-vst.png" alt="Delay VST3" style="max-width: 680px; margin: auto; padding-top: 15px" />

<style>
h1 {
  background-image: linear-gradient(45deg, rgb(60, 122, 77) 10%, rgb(63, 167, 86) 20%);
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# The Evolution of Audio DSP Plugins

<div class="grid grid-cols-2 gap-14 text-left text-lg mt-10">

<div v-click.animate-fade>
  <h3 class="text-xl font-bold mb-2">VST (1996)</h3>
  <ul class="text-md">
    <li>Steinberg's Virtual Studio Technology</li>
    <li>First plugin format to gain wide traction</li>
    <li>Enabled commercial DAW plugin ecosystems</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-xl font-bold mb-2">RTAS (1999) → AAX (2011)</h3>
  <ul class="text-md">
    <li>Avid’s real-time native plugin format</li>
    <li>DSP-accelerated plugins for Pro Tools HD</li>
    <li>(AAX) 64-bit plugin support in Pro Tools</li>
  </ul>
</div>

<div v-click.animate-fade>
  <h3 class="text-xl font-bold mb-2">Audio Units (2002)</h3>
  <ul class="text-md">
    <li>Apple's native plugin format (AU)</li>
    <li>Core to Logic Pro and GarageBand</li>
    <li>Still dominant on macOS and iOS</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-xl font-bold mb-2">LV2 (2008)</h3>
  <ul class="text-md">
    <li>Linux-native plugin format</li>
    <li>Modular and metadata-rich</li>
    <li>Powering JACK/Ardour-based systems</li>
  </ul>
</div>

</div>

<style>
h1 {
  background-image: linear-gradient(45deg, rgb(60, 122, 77) 10%, rgb(63, 167, 86) 20%);
  padding-top: 8px;
  padding-bottom: 4px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# How do we build cross-platform/format plugins?

<div class="grid grid-cols-1 md:grid-cols-2 gap-12 text-left text-lg mt-12">

<div v-click>
  <h3 class="text-xl text-red-300 font-bold mb-2">Option 1</h3>
  <div class="grid grid-cols-3 mt-4 mb-4">
    <img src="/plugin-vst-logo.png" alt="VST Logo" class="w-30 h-auto" />
    <img src="/plugin-aax-logo.png" alt="VST Logo" class="w-30 h-auto" />
    <img src="/plugin-au-logo.png" alt="VST Logo" class="w-17 h-auto mt-3" />
  </div>
  <ul class="text-xl text-red-300">
    <li>Use separate SDKs for each plugin format</li>
    <li>Manually manage plugin APIs</li>
    <li>Different build systems and wrappers</li>
    <li>Time-consuming to maintain and port</li>
    <li>Hard to test and debug across platforms</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-xl text-green-300 font-bold mb-2">Option 2</h3>
  <img src="/juce.png" alt="JUCE Logo" class="w-70 h-auto mb-8 mt-8" />
  <ul class="text-xl text-green-300">
    <li>C++ Audio DSP Framework</li>
    <li>Released in 2004</li>
    <li>Cross-compile VST/AU/RTAS/AAX/LV2</li>
    <li>Built-in GUI, DSP, MIDI, plugin wrappers</li>
    <li>Widely adopted by audio DSP developers</li>
  </ul>
</div>

</div>

<style>
h1 {
  background-image: linear-gradient(45deg, rgb(60, 122, 77) 10%, rgb(63, 167, 86) 20%);
  padding-top: 8px;
  padding-bottom: 4px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
p {
  padding-top: 4px;
}
</style>

---

<img src="/juce.png" alt="JUCE Logo" class="w-50 h-auto mb-8" />

<div class="grid grid-cols-2 gap-6 mt-6">

  <!-- PluginProcessor Column -->
  <div v-click>
    <div class="rounded-2xl border border-orange-400 p-4 shadow-md">
      <h4 class="text-2xl font-bold text-white mb-4">🎛️ Plugin Processor (DSP)</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Handles audio DSP processing</li>
      </ul>
    </div>
  </div>

  <!-- PluginEditor Column -->
  <div v-click>
    <div class="rounded-2xl border border-yellow-400 p-4 shadow-md">
      <h4 class="text-2xl font-bold text-white mb-4">🖼️ Plugin Editor (UI)</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Draws the plugin GUI</li>
      </ul>
    </div>
  </div>

  <!-- Desktop/Standalone -->
  <div v-click class="col-span-2">
  <Arrow top="13rem" left="24rem" height="5rem" />
  <Arrow top="13rem" left="51rem" height="5rem" />
    <div class="rounded-2xl border border-green-400 p-4 shadow-md">
      <h4 class="text-2xl font-bold text-white mb-4">🖥️ Desktop / DAW Plugin</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Desktop Standalone App or Plugin (VST/RTAS/LV2/AU etc.)</li>
      </ul>
    </div>
  </div>

   <!-- Headless DSP processor -->
  <div v-click>
  <Arrow top="13rem" left="28rem" height="14rem" />
    <div class="rounded-2xl border border-pink-400 p-4 shadow-md">
      <h4 class="text-2xl font-bold text-white mb-4">Headless Embedded DSP processor</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Audio processing with headless DSP plugins</li>
      </ul>
    </div>
  </div>

  <!-- PluginEditor Column -->
  <div v-click>
  <Arrow top="13rem" left="55rem" height="14rem" />
    <div class="rounded-2xl border border-blue-400 p-4 shadow-md">
      <h4 class="text-2xl font-bold text-white mb-4">Decoupled Web UI</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Client side GUI - Remote control processor</li>
      </ul>
    </div>
  </div>

</div>

---

# Running Audio Plugins on Embedded Systems

<div class="grid grid-cols-1 md:grid-cols-2 gap-12 text-left text-lg mt-12">

<div v-click>
  <img src="/elk.png" alt="JUCE Logo" class="h-28 mb-12" />
  <h3 class="mb-2">(2017)</h3>
  <ul class="text-xl">
    <li>Dual-kernel headless Linux OS</li>
    <li>Ultra-low audio latency ( < 0.3 ms )</li>
    <li>Headless DAW / Plugin host ( Sushi )</li>
    <li>Made in Sweden</li>
  </ul>
</div>

<div v-click>
  <img src="/elkos-aarch.png" alt="ElkOS ARM64" style="max-height: 34vh; margin: auto;" />
</div>

</div>

<style>
h1 {
  background-image: linear-gradient(45deg, rgb(60, 122, 77) 10%, rgb(63, 167, 86) 20%);
  padding-top: 8px;
  padding-bottom: 4px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
p {
  padding-top: 4px;
}
</style>

---

<div class="grid grid-cols-3 items-center justify-items-center gap-6 mt-4">

  <!-- Left Column (ElkOS) -->
  <div>
    <div class="rounded-2xl border border-white p-8 shadow-md w-64">
      <img src="/elk.png" alt="ElkOS" class="w-40 p-4 mb-4 mx-auto" />
      <div class="space-y-4 text-white">
        <div class="rounded-2xl border border-yellow-200 p-2 text-center shadow-md">Sushi (DAW)</div>
        <div class="rounded-2xl border border-grey-400 p-2 text-center shadow-md">Linux OS</div>
        <div class="rounded-2xl border border-grey-400 p-2 text-center shadow-md">Xenomai RTOS</div>
      </div>
    </div>

  </div>

  <!-- Center (gRPC logo) -->
  <div class="flex items-center justify-center">
    <img src="/grpc.png" alt="gRPC Logo" class="w-45 h-auto" />
  </div>

  <!-- Right Column (Tonalflex) -->
  <div>
    <div class="rounded-2xl border border-white p-8 shadow-md w-64">
      <img src="/logo.svg" alt="Tonalflex" class="w-60 p-1 mb-8 mx-auto" />
      <div class="rounded-2xl border border-white pl-1 shadow-md">
        <div class="flex items-center justify-center p-2">
          <span>Plugins</span>
          <img src="/cpp.png" alt="Python Logo" class="ml-2 w-6 h-6" />
          <img src="/juce.png" alt="Python Logo" class="ml-1 w-13 h-4" />
        </div>
      </div>
      <div class="flex justify-center">
        <div class="m-2 w-60 h-0.2 bg-white my-4"></div> <!-- vertical line -->
      </div>
      <div class="space-y-4 text-white">
        <div class="rounded-2xl border border-yellow-400 pl-4 shadow-md">
          <div class="flex items-center justify-center">
            <span>Butler</span>
            <img src="/python.png" alt="Python Logo" class="w-10 h-10" />
          </div>
        </div>
        <div class="rounded-2xl border border-purple-400 p-2 text-center shadow-md">
          <img src="/envoy.png" alt="Envoy Logo" class="w-20 mx-auto brightness-200" />
        </div>
        <div class="rounded-2xl border border-blue-400 shadow-md">
          <div class="flex items-center justify-center gap-1 p-2">
            <span>Remote UI</span>
            <img src="/ts.png" alt="TypeScript Logo" class="ml-2 w-5 h-5" />
            <img src="/vue.png" alt="Vue Logo" class="w-5 h-5" />
          </div>
        </div>
        <!-- <div class="rounded-2xl border border-white p-2 text-center shadow-md">Plugins (VST3)</div> -->
      </div>
    </div>

  </div>

</div>

---

<section class="text-white">
  <h1 class="text-3xl font-bold text-center pb-4">Remote Control Web UI</h1>

  <div class="grid grid-cols-3">
    <!-- General UI -->
    <div class="flex justify-center items-center">
      <img src="/ios-plugins.png" alt="Image 1" class="w-50 h-auto" />
    </div>
     <!-- TypeScript + Vue -->
    <div class="flex justify-center gap-3 items-center">
      <img src="/ts.png" alt="Image 1" class="w-30 h-auto" />
      <img src="/vue.png" alt="Image 1" class="w-30 h-auto" />
    </div>
    <!-- Plugin -->
    <div class="flex justify-center items-center">
      <img src="/ios-delay.png" alt="Image 2" class="w-50 h-auto" />
    </div>

  </div>
</section>

---

<section class="text-white">
  <h1 class="text-3xl font-bold text-center">Neural Amp Modeler: Capture</h1>
  <!-- <h2 class="text-3xl font-bold text-left pb-4">Profile Analog Hardware</h2> -->
  <div class="flex flex-row justify-center items-center gap-8 mt-8">
    <div class="flex flex-col items-center text-center">
      <p class="text-xl font-semibold mb-4">Calibrated Input</p>
      <img src="/audio-wave.png" alt="Input"
           class="w-48 h-auto rounded-2xl border-2 border-white shadow-lg" />
    </div>
    <div class="text-6xl text-green mt-18">→</div>
    <div class="flex flex-col items-center text-center">
      <p class="text-xl font-semibold mb-4">Analog Audio Hardware</p>
      <img src="/nam/amp-marshall-plexi.png" alt="Hardware"
           class="w-60 h-auto rounded-2xl border-2 border-white shadow-lg mb-4 p-2" />
      <img src="/nam/amp-neve-1073.jpg" alt="Hardware"
           class="w-60 h-auto rounded-2xl border-2 border-white shadow-lg" />
    </div>
    <div class="text-6xl text-green mt-18">→</div>
    <div class="flex flex-col items-center text-center">
      <p class="text-xl font-semibold mb-4">Processed Output</p>
      <img src="/audio-wave.png" alt="Output"
           class="w-48 h-auto rounded-2xl border-2 border-white shadow-lg" />
    </div>
  </div>
</section>

<style>
h1 {
  background-image: linear-gradient(45deg, rgb(60, 122, 77) 10%, rgb(63, 167, 86) 20%);
  padding-top: 8px;
  padding-bottom: 4px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

<section class="text-white">
  <h1 class="text-3xl font-bold text-center pb-4">Neural Amp Modeler: Profiling</h1>
  <!-- <h2 class="text-3xl font-bold text-left pb-4">Profile Analog Hardware</h2> -->
  <div class="flex flex-row justify-center items-center gap-8 mt-8">
    <div class="flex flex-col items-center text-center">
      <p class="text-xl font-semibold mb-4">Calibrated Input</p>
      <img src="/audio-wave.png" alt="Input"
           class="w-48 h-auto rounded-2xl border-2 border-white shadow-lg" />
      <div class="mt-4"></div>
      <p class="text-xl font-semibold mb-4">Processed Output</p>
      <img src="/audio-wave.png" alt="Output"
           class="w-48 h-auto rounded-2xl border-2 border-white shadow-lg" />
    </div>
    <div>
      <div class="text-6xl text-green mt-18">→</div>
      <div class="text-6xl text-green mt-28">→</div>
    </div>
    <div class="flex flex-col items-center text-center">
      <p class="text-xl font-semibold mb-4">NAM Neural Trainer</p>
      <img src="/nam/pytorch-logo.png" alt="Hardware"
           class="w-55 h-auto rounded-2xl border-2 border-white shadow-lg" />
    </div>
    <div class="text-6xl text-green mt-18">→</div>
    <div class="flex flex-col items-center text-center">
      <p class="text-xl font-semibold mb-4">NAM Profile</p>
      <div class="w-40 rounded-2xl border-2 border-white shadow-lg flex flex-col items-center">
        <img src="/nam/json-logo.png" alt="NAM File"
            class="w-30 h-auto p-4 pb-0 mt-2" />
        <p class="text-sm text-white px-2">
          Digital capture of hardware sound
        </p>
      </div>
    </div>
  </div>
</section>

<style>
h1 {
  background-image: linear-gradient(45deg, rgb(60, 122, 77) 10%, rgb(63, 167, 86) 20%);
  padding-top: 8px;
  padding-bottom: 4px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

<section class="text-white">
  <h1 class="text-3xl font-bold text-center pb-2">Neural Amp Modeler: Core</h1>
  <div class="flex flex-row justify-center items-center gap-6 max-w-screen-xl mx-auto mt-12">
    <div class="flex flex-col items-center text-center max-w-[10rem] shrink-0">
      <p class="text-md font-semibold mb-2">Input</p>
      <img src="/audio-wave.png" alt="Input" class="w-50 h-auto rounded-2xl border-2 border-white shadow-md" />
    </div>
    <div class="text-6xl text-green-400 mt-16">→</div>
    <div class="flex flex-col items-center text-center">
      <p class="text-xl font-semibold mb-4">Plugin</p>
      <img src="/neuralamp-plugin.png" alt="Hardware"
           class="w-35 h-auto rounded-2xl border-2 border-white shadow-lg mb-4 p-2" />
    </div>
    <div class="relative w-13 h-13 items-center mt-10">
      <div class="absolute inset-0 animate-spin-slow opacity-30">
        <img src="/repeat.png" alt="Spinning Arrow" class="w-full h-full" />
      </div>
    </div>
    <div class="flex flex-col items-center text-center">
      <p class="text-xl font-semibold mb-4">NAM Core</p>
      <img src="/NAM.png" alt="Hardware"
           class="w-23 h-auto rounded-2xl border-2 border-white shadow-lg mb-4 p-4" />
      <div class="w-23 rounded-2xl border-2 border-white shadow-lg flex flex-col items-center">
        <img src="/nam/json-logo.png" alt="NAM File"
            class="w-20 h-auto p-4 pb-0 mt-0" />
        <p class="text-sm text-white px-0">
          NAM Profile
        </p>
      </div>
    </div>
    <div class="text-6xl text-green-400 -mt-16">→</div>
    <div class="flex flex-col items-center text-center max-w-[10rem] shrink-0 mt-0">
      <p class="text-md font-semibold mb-2">Processed Output</p>
      <img src="/audio-wave.png" alt="Output" class="w-50 h-auto rounded-2xl border-2 border-white shadow-md" />
      <p class="text-sm">that sounds like...</p>
      <img src="/nam/amp-marshall-plexi.png" alt="Hardware"
           class="w-60 h-auto rounded-2xl border-2 border-white shadow-lg -mt-4 p-2" />
    </div>

  </div>
</section>

<style>
h1 {
  background-image: linear-gradient(45deg, rgb(60, 122, 77) 10%, rgb(63, 167, 86) 20%);
  padding-top: 8px;
  padding-bottom: 4px;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
p {
  padding-top: 4px;
}
@keyframes spin-slow {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}
.animate-spin-slow {
  animation: spin-slow 6s linear infinite;
}
</style>

---

<section class="text-white">
  <h1 class="text-3xl font-bold text-center pb-4">Hardware Prototype</h1>
  <img src="/hw-idea.png" alt="Tonalflex" class="w-180 p-1 mb-8 mx-auto" />
</section>

---

<section class="text-white text-center py-12">
  <h2 class="text-3xl font-bold mb-4">Thank You!</h2>
  <img src="/tonalflex-qr-link.png" alt="Tonalflex" class="w-70 p-2 mb-8 mx-auto" />
  <p class="text-lg max-w-xl mx-auto text-center">
  Join the journey of open-sourcing audio!
</p>
</section>
