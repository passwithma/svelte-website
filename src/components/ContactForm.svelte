<script>

    import emailjs from 'emailjs-com';
    export let activeGearItem

    import{ init } from 'emailjs-com';
    init("user_Mwx2wKXM9KCrpglLhd9cO");

    let success = false;
    let failure = false;

    function submitForm(e) {
        e.preventDefault();
        emailjs.sendForm(activeGearItem, activeGearItem, e.target)
        .then(function(response) {
            success = true;
            e.target.reset()
        }, function(error) {
            failure = true;
        })
        e.reset()
    }

    let instructor = ["Martin Fender", "07961 290 283"];

    $: if (activeGearItem === "Automatic") {
        instructor = ["Allen Stanley", "07712 778 392"];
    } else {
        instructor = ["Martin Fender", "07961 290 283"];
    }

</script>

{#if success && !failure}<h3>Contact Form Submitted. We will be in contact shortly.</h3>{/if}
{#if failure && !success}<h3>Contact Form Not Submitted. Please try again or call on the number below.</h3>{/if}
<h4>Please ensure that the correct option is chosen in the automatic/manual selector above before clicking send on the contact form. This will ensure that your message gets to the correct team.</h4>
<h4>Or call {instructor[0]} on {instructor[1]}</h4>
<div class="container">
<div class="contact-form-container" class:A={activeGearItem === "Automatic"} class:M={activeGearItem === "Manual"} on:click={() => ""}>
    <form id="contact-form" on:submit={submitForm}>
        <label for="name">Name</label>
        <input id="name" type="text" name="name">
        <label for="email">Email</label>
        <input id="email" type="email" name="email">                
        <label for="number">Contact Number</label>
        <input id="number" type="tel" name="number">
        <label for="message">Message</label>
        <input id="message" name="message">
        <input type="hidden" id="gearbox" name="gearbox" value={activeGearItem}>
        <label for="submit-button"></label>
        <input id="submit-button" type="submit" value="Send">
    </form>
</div>
</div>



<style>

    .M {
        box-shadow: 3px 3px 3px 3px #981E32;
    }

    .A {
        box-shadow: 3px 3px 3px 3px #2e75b6;
    }

    label {
        text-align: center;
    }

    input {
        width: 600px;
        border-radius: 10px;
        display:flex;
        justify-content: center;
        padding-top: 0;
        padding-left: 0;
        line-height: 1em;
    }

    h4 {
        text-align: center;
    }

    h3 {
        text-align: center;
    }

    #submit-button {
        width: 250px;
        border-radius: 10px;
        justify-content: center;
    }

    .container {
        margin-left: auto;
        margin-right: auto;
        justify-content: center;
        padding-top: 10px;
        padding-bottom: 10%;
        display: flex;
    }

    form {
        justify-content: center;
    }

    .contact-form-container {
        background-color: white;
        border-radius: 10px;
        border: 2px solid black;
        padding: 10px;
        justify-content: center;
        align-items: center;
        width: 600px;
    }

    #message {
        height: 200px;
    }

    @media (max-width: 900px) {
        .contact-form-container {
            width: 300px;
        }
        input {
            width: 280px;
        }

        #submit-button {
            width: 280px;
        }
    }

</style>