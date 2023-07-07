<!-- ATTRIBUTE
@text = The element innerHTML/Content/Text
@duration = The duration of the glitch, bigger means slower glitch, lower means faster glitch
@class_ = The element's class
@style_ = The element's style

Example:<AType element="h1" text="I don't understand why but it feels really hard to actually confess this kind of selfish hate unto you. Lucifer." wpm=280 class_="text-red-500 text-3xl"/>
-->
<script>
  import { gsap } from "gsap";
  import { onMount } from "svelte";

  let glitch1;
  let glitch2;
  let glitch3;
  export let text = "null";
  export let duration = 0.03;
  export let class_;
  export let style_;

  onMount(() => {
    const tl1 = gsap.timeline({ repeat: -1 });

    for (let i = 0; i <= 20; i++) {
      tl1.to(glitch1, {
        clip: `rect(${Math.random() * 20}px, 9999px, ${Math.random() *
          100}px, 0)`,
        duration: duration
      });
    }

    const tl2 = gsap.timeline({ repeat: -1 });

    for (let i = 0; i <= 5; i++) {
      tl2.to(glitch2, {
        clip: `rect(${Math.random() * 100}px, 9999px, ${Math.random() *
          1000}px, 0)`,
        duration: duration
      });
    }

    const tl3 = gsap.timeline({ repeat: -1 });

    for (let i = 0; i <= 20; i++) {
      tl3.to(glitch3, {
        clip: `rect(${Math.random() * 10}px, 9999px, ${Math.random() * 10}px, )`,
        duration: duration
      });
    }
  });
</script>

<div class={`relative inline-block mx-4 group ${class_}`} style={`${style_}`}>
  <span bind:this={glitch1} class="glitch" style="position: absolute; left: 2px; text-shadow: -1px 0 red; overflow: hidden; clip: rect(0, 900px, 100px, 0);">
    {text}
  </span>
  <span bind:this={glitch2} class="glitch" style="position: absolute; left: -2px; text-shadow: 1px 0 blue; overflow: hidden; clip: rect(0, 900px, 100px, 0);">
    {text}
  </span>
</div>

<style>
</style>
