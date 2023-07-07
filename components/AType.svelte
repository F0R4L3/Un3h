<!-- ATTRIBUTE
@text = The element innerHTML/Content/Text
@wpm = Word per minute, how many word can be typed in 1 minute
@class_ = The element's class
@style_ = The element's style
@attribute_ = The element's attribute, *not useful*



Example:<AType element="h1" text="I don't understand why but it feels really hard to actually confess this kind of selfish hate unto you. Lucifer." wpm=280 class_="text-red-500 text-3xl"/>
-->
<script>
  import { gsap } from "gsap";
  import { tick, onMount } from "svelte";
  export let text;
  export let wpm;
  export let class_;
  export let style_;
  export let attribute_;
  export let element;
  let actual_text = "";
  let speed = 60 / wpm / 5;

  const tl = gsap.timeline();
  tick();
  onMount(async () => {
    text.split("").forEach((char, index) => {
      tl.add(() => (actual_text += char), speed * index);
    });
  }, -1);
</script>

{@html `<${element} class="${class_}" ${attribute_} style="${style_}">${actual_text}</${element}>`}
