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

# Audio DSP plugins on Embedded Devices?

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
    <div class="rounded-2xl border border-green-400 p-4 shadow-md">
      <h4 class="text-2xl font-bold text-white mb-4">🖥️ Desktop / DAW Plugin</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Desktop Standalone App or Plugin (VST/RTAS/LV2/AU etc.)</li>
      </ul>
    </div>
  </div>

   <!-- Headless DSP processor -->
  <div v-click>
    <div class="rounded-2xl border border-pink-400 p-4 shadow-md">
      <h4 class="text-2xl font-bold text-white mb-4">Headless DSP processor</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Handles audio DSP processing</li>
      </ul>
    </div>
  </div>

  <!-- PluginEditor Column -->
  <div v-click>
    <div class="rounded-2xl border border-blue-400 p-4 shadow-md">
      <h4 class="text-2xl font-bold text-white mb-4">Web UI (Decoupled)</h4>
      <ul class="list-disc list-inside text-white space-y-2">
        <li>Draws the plugin GUI</li>
      </ul>
    </div>
  </div>

</div>

---
