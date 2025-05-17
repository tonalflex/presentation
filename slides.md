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

# How do we make Audio DSP plugins cross-platform?

<div class="grid grid-cols-1 md:grid-cols-2 gap-12 text-left text-lg mt-12">

<div v-click>
  <img src="/juce.png" alt="JUCE Logo" class="w-90 h-auto mb-12" />
  <h3 class="mb-2">(2004)</h3>
  <ul class="text-xl">
    <li>C++ audio DSP framework</li>
    <li>Cross-compile VST/AU/RTAS/AAX/LV2</li>
    <li>Built-in GUI, DSP, MIDI, plugin wrappers</li>
    <li>Widely adopted by audio DSP developers</li>
  </ul>
</div>

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

<!-- --- -->

<!-- <img src="/elkos-aarch.png" alt="ElkOS ARM64" style="max-height: 58vh; margin: auto;" /> -->

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
      <h4 class="text-2xl font-bold text-white mb-4">Headless DSP processor</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Handles audio DSP processing</li>
      </ul>
    </div>
  </div>

  <!-- PluginEditor Column -->
  <div v-click>
  <Arrow top="13rem" left="55rem" height="14rem" />
    <div class="rounded-2xl border border-blue-400 p-4 shadow-md">
      <h4 class="text-2xl font-bold text-white mb-4">Web UI (Decoupled)</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Draws the plugin GUI</li>
      </ul>
    </div>
  </div>

</div>

---

<h1>DAW Desktop DSP Plugin</h1>
<img src="/delay-vst.png" alt="Delay VST3" style="max-width: 720px; margin: auto;" />

---

<h1>Embedded Remote Control UI</h1>

---

<!-- Wrapper: 3 equal columns, center-aligned -->
<div class="grid grid-cols-3 items-center justify-items-center gap-6 mt-4">

  <!-- Left Column (ElkOS) -->
  <div>
    <div class="rounded-2xl border border-white p-8 shadow-md w-64">
      <img src="/elk.png" alt="ElkOS" class="w-40 p-4 mb-4 mx-auto" />
      <div class="space-y-4 text-white">
        <div class="rounded-2xl border border-grey-400 p-2 text-center shadow-md">Linux OS</div>
        <div class="rounded-2xl border border-yellow-200 p-2 text-center shadow-md">Sushi</div>
        <div class="rounded-2xl border border-red-400 p-2 text-center shadow-md">Raspa</div>
        <div class="flex justify-center">
          <div class="m-2 w-60 h-0.2 bg-white"></div> <!-- vertical line -->
        </div>
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
      <div class="space-y-4 text-white">
        <div class="rounded-2xl border border-blue-400 shadow-md">
          <div class="flex items-center justify-center gap-1 p-2">
            <span>Remote UI</span>
            <img src="/ts.png" alt="TypeScript Logo" class="ml-2 w-5 h-5" />
            <img src="/vue.png" alt="Vue Logo" class="w-5 h-5" />
          </div>
        </div>
        <div class="rounded-2xl border border-purple-400 p-2 text-center shadow-md">
          <img src="/envoy.png" alt="Envoy Logo" class="w-20 mx-auto brightness-200" />
        </div>
        <div class="rounded-2xl border border-yellow-400 pl-4 shadow-md">
          <div class="flex items-center justify-center">
            <span>Butler</span>
            <img src="/python.png" alt="Python Logo" class="w-10 h-10" />
          </div>
        </div>
        <div class="flex justify-center">
          <div class="m-2 w-60 h-0.2 bg-white"></div> <!-- vertical line -->
        </div>
        <div class="rounded-2xl border border-white pl-1 shadow-md">
          <div class="flex items-center justify-center p-2">
            <span>Plugins</span>
            <img src="/cpp.png" alt="Python Logo" class="ml-2 w-6 h-6" />
            <img src="/juce.png" alt="Python Logo" class="ml-1 w-13 h-4" />
          </div>
        </div>
        <!-- <div class="rounded-2xl border border-white p-2 text-center shadow-md">Plugins (VST3)</div> -->
      </div>
    </div>

  </div>

</div>

---

---
