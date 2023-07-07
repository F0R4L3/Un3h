<script>
  import AType from './components/AType.svelte';
  import Tooltip from './components/Tooltip.svelte';
  import GlitchText from './components/GlitchText.svelte';
  import Slide from './components/Slide.svelte';
  import Nav from './uhhYUHHHH/Nav.svelte';
  import Blog from './uhhYUHHHH/Blog.svelte';
  import Home from './uhhYUHHHH/Home.svelte';
  import Credit from './uhhYUHHHH/Credit.svelte';
  /////////////////////////////////////////////////////////
  /*
                                                     	function changeTheme() {
                                                       	const button_theme_tl = gsap.timeline();
                                                       	isDark = !isDark;
                                                       	console.log(isDark);
                                                       	if (isDark == true) {
                                                       		// Fix theme
                                                       		button_theme_tl
                                                       			.to('#theme-sun-icon', { y: '+40', ease: 'bounce' })
                                                       			.to('#theme-moon-icon', { y: '-40', ease: 'bounce' });
                                                       	}
                                                       }

                                                       function slideshow(node, { screens }) {
                                                       	// Get all the screens
                                                       	const screenElements = node.querySelectorAll(screens);

                                                       	// Create a GSAP timeline
                                                       	const timeline = gsap.timeline({ paused: true });

                                                       	// Animate each screen
                                                       	screenElements.forEach((screen, index) => {
                                                       		timeline.to(screen, {
                                                       			autoAlpha: index === 0 ? 1 : 0, // Show the first screen, hide the others
                                                       			zIndex: index === 0 ? 1 : 0, // Bring the first screen to the front, push others back
                                                       			duration: 1
                                                       		});
                                                       	});

                                                       	// Return an object with methods to control the slideshow
                                                       	return {
                                                       		next() {
                                                       			timeline.play();
                                                       		},
                                                       		prev() {
                                                       			timeline.reverse();
                                                       		}
                                                       	};
                                                       }
                                                     	*/
</script>

<style>
  main {
  	font-family: Poppins;
  	text-align: center;
  }
</style>

<main class="w-screen h-screen bg-gray-900">
	<Nav />
	<!-- <Home /> -->
	<!-- <Blog /> -->
	<Credit />
</main>

