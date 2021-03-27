<script>
	import Header from './components/Header.svelte';
	import Home from './pages/home.svelte'
	import Testimonials from './pages/testimonials.svelte'
	import Pricing from './pages/pricing.svelte'
	import ContactForm from './components/ContactForm.svelte'
	import GearSelector from './components/GearSelector.svelte'


	//navigation
	let items = ['Home', 'Testimonials', 'Pricing', 'Contact'];
	let activeItem = 'Home';
	let overlay = false;
	const navChange = (e) => activeItem = e.detail;
	function contactOverlay() {
		overlay = !overlay;
	}


	//automatic / manual switch logic to set the variables ready to be sent as props to allow the website to be used for both exclusively.
	let gearItems = ['Manual', 'Automatic'];
	let activeGearItem = 'Manual';
	let hourPrice = 35
	const toggleGearbox = (e) => {
        activeGearItem = e.detail;
		if (activeGearItem == "Manual") {
			hourPrice = 35;
		} else if (activeGearItem == "Automatic"){
			hourPrice = 30;
		}
    };
</script>

<svelte:head>
	<title>A&M Driving School</title>
</svelte:head>

<Header  {activeGearItem} {activeItem} {items} on:tabChange={navChange} />
<GearSelector items={gearItems} activeItem={activeGearItem} on:tabChange={toggleGearbox} />

<main class:manual={activeGearItem === "Manual"} class:automatic={activeGearItem === "Automatic"}>
	<div class="container">
		{#if activeItem === 'Home'}
			<Home {activeGearItem} {hourPrice} />
		{:else if activeItem === 'Testimonials'}
			<Testimonials {activeGearItem} />
		{:else if activeItem === 'Pricing'}
			<Pricing {activeGearItem} {hourPrice} />
		{:else if activeItem === 'Contact'}
			<ContactForm {activeGearItem} />
		{/if}
	</div>
</main>


<style>

	main {
		margin: 0;
		min-height: 750px;
	}

	.manual {
		background-image: url("/images/backgroundlogo75Manual.png");
		background-position: center;
		background-repeat: no-repeat;
	}

	.automatic {
		background-image: url("/images/backgroundlogo75Automatic.png");
		background-position: center;
		background-repeat: no-repeat;
	}

	.container {
		overflow-y: hidden;
		overflow-x: hidden;
	}

	@media(max-width:1219px) {
		main {
			overflow: auto;
		}
	}

	@media(max-width:100px) {
		.container {
			background-size: 100%;
		}
	}
</style>