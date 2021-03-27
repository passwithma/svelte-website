<script>

    import CoursePricing from './CoursePricing.svelte'

    export let hourPrice;
    export let activeGearItem;

    $: twoHourPrice = (hourPrice * 2) - 1;
    $: tenHourPrice = (hourPrice - 1) * 10;
    $: courseHourly = hourPrice - 1;
    $: testBoosterCourse = (courseHourly * 15) + 62;
    $: midPassCourse = (courseHourly * 20 ) + 62;
    $: semiIntensiveCourse = (courseHourly * 30) + 62;
    let courseVersions = ['Test Booster Course', 'Midway Pass Course', 'Semi-Intensive Course', 'One Week Pass Course'];
    let hidden1 = true, hidden2 = true, hidden3 = true, hidden4 = true;

</script>

<div class="wrapper">
    <h3 class="courses">Lessons</h3>
</div>

<div class="wrapper">
    <div class="container">
        <h3 class="hourlyPricing">1 Hour: </h3>
        <h3 class="hourlyPricing">£{hourPrice}</h3>
    </div>
    <div class="container center">
        <h3 class="hourlyPricing">2 Hours: </h3>
        <h3 class="hourlyPricing">£{twoHourPrice}</h3>
    </div>
    <div class="container">
        <h3 class="hourlyPricing">10 Hours: </h3>
        <h3 class="hourlyPricing">£{tenHourPrice}</h3>
    </div>
</div>

<div class="wrapper">
    <h3 class="courses">Courses</h3>
</div>


<li class:clickedA={!hidden1 && activeGearItem === "Automatic"} class:clickedM={!hidden1 && activeGearItem === "Manual"} class="click" on:click="{() => {
    hidden1 = !hidden1;
    hidden2 = true;
    hidden3 = true;
    hidden4 = true;
}}">{courseVersions[0]}</li>
<div class:hidden={hidden1}>
    <CoursePricing {courseHourly} courseVersion={courseVersions[0]} />
    <p class:pricingA={activeGearItem === "Automatic"} class:pricingM={activeGearItem === "Manual"} class:hidden={hidden1}>£{testBoosterCourse}</p>
</div>

<li class:clickedA={!hidden2 && activeGearItem === "Automatic"} class:clickedM={!hidden2 && activeGearItem === "Manual"} class="click" on:click="{() => {
    hidden1 = true;
    hidden2 = !hidden2;
    hidden3 = true;
    hidden4 = true;
    }}">{courseVersions[1]}</li>
<div class:hidden={hidden2}>
    <CoursePricing {courseHourly} courseVersion={courseVersions[1]} />
    <p class:pricingA={activeGearItem === "Automatic"} class:pricingM={activeGearItem === "Manual"} class:hidden={hidden2}>£{midPassCourse}</p>
</div>

<li class:clickedA={!hidden3 && activeGearItem === "Automatic"} class:clickedM={!hidden3 && activeGearItem === "Manual"}  class="click" on:click="{() => {
    hidden1 = true;
    hidden2 = true;
    hidden3 = !hidden3;
    hidden4 = true;
    }}">{courseVersions[2]}</li>
<div class:hidden={hidden3}>
    <CoursePricing {courseHourly} courseVersion={courseVersions[2]} />
    <p class:pricingA={activeGearItem === "Automatic"} class:pricingM={activeGearItem === "Manual"} class:hidden={hidden3}>£{semiIntensiveCourse}</p>
</div>

<li class:clickedA={!hidden4 && activeGearItem === "Automatic"} class:clickedM={!hidden4 && activeGearItem === "Manual"}  class="click" on:click="{() => {
    hidden1 = true;
    hidden2 = true;
    hidden3 = true;
    hidden4 = !hidden4;
    }}">{courseVersions[3]}</li>
<div class:hidden={hidden4}>
    <CoursePricing {courseHourly} courseVersion={courseVersions[3]} />
    {#if hourPrice == 35}
        <p class:pricingA={activeGearItem === "Automatic"} class:pricingM={activeGearItem === "Manual"} class:hidden={hidden4}>£1220</p>
    {:else if hourPrice == 30}
        <p class:pricingA={activeGearItem === "Automatic"} class:pricingM={activeGearItem === "Manual"} class:hidden={hidden4}>£1100</p>
    {/if}
</div>


<style>

    li {
        font-size: 1.17em;
        font-weight: bolder;
        padding: 5px;
        list-style-position: inside;
        list-style-type: disclosure-closed;
    }

    .center {
        border-right: 3px solid #9A9B9C;
        border-left: 3px solid #9A9B9C;
    }

    .hourlyPricing {
        margin: 25px;
    }

    .wrapper {
        display:flex;
        width: 100%;
        text-align: center;
        justify-content: center;
    }

    .courses {
        border-top: 3px solid #9A9B9C;
        padding-top:10px;
        width: 100%;
    }

    .hidden {
        display: none;
    }

    .click {
        cursor: pointer;
    }

    .clickedM {
        justify-content: center;
        list-style-type: disclosure-open;
        color: #981E32;
    }

    .clickedA {
        justify-content: center;
        list-style-type: disclosure-open;
        color: #2e75b6;
    }
    

    .pricingM {
        font-size: 15;
        font-weight: bold;
        color: #981E32;
    }

    .pricingA {
        font-size: 15;
        font-weight: bold;
        color: #2e75b6;
    }

</style>