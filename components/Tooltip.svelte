<!-- Attribute

@element = The element being used
@content = The innerHTML/Text/Content of the element being used
@attribute = The Attribute of the element, useful for link. e.g. <a href="">content</a>
@class_ = The element class
@style = The element style/CSS
@tooltipContent = The element's tooltip innerHTML/Text/Content
@tooltipStyle = The element's tooltip style/CSS
@tooltipClass = The element's tooltip classes
@waitAppear = How many seconds will the tooltip appear.
@waitDissappear = How many seconds will the tooltip disappear.

Example:
<Tooltip 

class_="bg-sky-500 text-white p-6 rounded-full shadow-lg" 
element="a" 
attribute_='href="https://id.pinterest.com/pin/17381148554518534/"' 
content="Click me! or maybe hover me?" 
waitAppear=.2 
waitDissappear=.5 
tooltipContent="Random pinterest!" 
tooltipClass="bg-red-500 text-white -translate-y-5"

/>
-->
<script>
  import { gsap } from "gsap";
  export let element;
  export let content;
  export let class_;
  export let style_;
  export let tooltipContent;
  export let tooltipStyle;
  export let tooltipClass;
  export let waitAppear;
  export let waitDissappear;
  export let attribute_;
  let _tooltip;
  var color = "red";

  function hover() {
    setTimeout(() => {
      gsap.to(_tooltip, { opacity: 1 });
      gsap.to(_tooltip, { display: "inline-flex" });
    }, waitAppear * 1000);
  }
  function _hover() {
    setTimeout(() => {
      gsap.to(_tooltip, { opacity: 0 });
      gsap.to(_tooltip, { display: "none" });
    }, waitDissappear * 1000);
  }

  let inz = `<${element} ${attribute_} class="${class_}" style="${style_}">${content}</${element}>`;
</script>

<style>
</style>

<div class="group relative inline-block">
  <div on:mousemove={hover} on:mouseleave={_hover} >
    {@html inz}
  </div>
  <span bind:this={_tooltip} class={`opacity-0 p-1 rounded-lg absolute bottom-full left-2/4 -translate-x-2/4 mb-1 ${tooltipClass} `} style={`${tooltipStyle}`}>{tooltipContent}</span>
  <!-- padding:5px;border-radius:5px;position:absolute;opacity:0;display:none; -->
</div>

<!-- 
  <div class="group relative inline-block">
  Hover me
  <span class="absolute hidden group-hover:block bg-gray-700 text-white px-2 py-1 rounded text-sm -top-8 -left-1/2 translate-x-1/2">
    Tooltip content
  </span>
</div>
-->
