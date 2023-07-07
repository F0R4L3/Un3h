<script>
  import { onMount, onDestroy } from 'svelte';
  import { TweenMax, Power2, TimelineMax } from 'gsap';
  import { gsap } from 'gsap';

  let slides = [
  	{ id: 1, title: 'Slide 1' },
  	{ id: 2, title: 'Slide 2' },
  	{ id: 3, title: 'Slide 3' }
  ];
  let activeSlide = slides[0];
  let nextSlide = slides[1];
  let prevSlide = slides[slides.length - 1];
  let slideElements = [];
  let tl;

  onMount(() => {
  	tl = new TimelineMax();
  	tl.to(slideElements[0], { autoAlpha: 1, ease: Power2.easeInOut });
  });

  onDestroy(() => {
  	tl.kill();
  });

  function next() {
  	let currentIndex = slides.findIndex(slide => slide.id === activeSlide.id);
  	let nextIndex = currentIndex + 1 === slides.length ? 0 : currentIndex + 1;
  	prevSlide = activeSlide;
  	activeSlide = slides[nextIndex];
  	nextSlide = slides[nextIndex + 1] || slides[0];
  	animate();
  }

  function prev() {
  	let currentIndex = slides.findIndex(slide => slide.id === activeSlide.id);
  	let prevIndex = currentIndex - 1 < 0 ? slides.length - 1 : currentIndex - 1;
  	nextSlide = activeSlide;
  	activeSlide = slides[prevIndex];
  	prevSlide = slides[prevIndex - 1] || slides[slides.length - 1];
  	animate();
  }

  function animate() {
  	tl.clear();
  	tl.to(slideElements[slides.findIndex(slide => slide.id === prevSlide.id)], {
  		autoAlpha: 0,
  		ease: Power2.easeInOut
  	});
  	tl.to(slideElements[slides.findIndex(slide => slide.id === activeSlide.id)], {
  		autoAlpha: 1,
  		ease: Power2.easeInOut
  	});
  }
</script>

<button on:click={prev}>Prev</button>
<button on:click={next}>Next</button>

<div class="slides">
  {#each slides as slide (slide.id)}
    <div
      class="slide"
      bind:this={slideElements[slide.id - 1]}
      style="opacity: {slide.id === activeSlide.id ? '1' : '0'}"
    >
      {slide.title}
    </div>
  {/each}
</div>

<style>
  .slides {
  	position: relative;
  	height: 100vh;
  	overflow: hidden;
  }
  .slide {
  	position: absolute;
  	top: 0;
  	left: 0;
  	width: 100%;
  	height: 100%;
  	display: flex;
  	justify-content: center;
  	align-items: center;
  	font-size: 2rem;
  	background: #f0f0f0;
  	transition: opacity 1s;
  }
</style>
