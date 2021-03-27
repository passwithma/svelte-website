<script>

    import TestimonialCard from '../components/TestimonialCard.svelte'
    export let activeGearItem

    const toggleTestimonials = (e) => {
        activeItem = e.detail;
    }

    let manualphoto1 = 'manualphoto1.jpeg'
    let manualtext1 = 'Martin was a brilliant instructor! He was understanding, knowledgable and friendly and and got me a first time pass. I can not recommend him enough, his lessons are something I looked forward to every week! Thanks Martin.'
    let manualphoto2 = 'manualphoto2.jpeg'
    let manualtext2 = '1st Time Pass with Martin!'
    let manualphoto3 = 'manualphoto3.jpeg'
    let manualtext3 = 'I recently had the privilege of having Martin Fender as my driving instructor. Although I only had a few lessons Martin quickly figured out where my strength and weaknesses were. Martin is great instructor, explained things very well, always friendly and very accommodating. Martin has a great demeanor and has a great sense of humor. Thank you very much Martin, God Bless.'
    let manualphoto4 = 'manualphoto4.jpeg' 
    let manualtext4 = '1st Time Pass with 0 Minors!!'
    let manualphoto5 = 'manualphoto5.jpeg'
    let manualtext5 = "I am going to start by saying that my first driving instructor from another driving school wasn't the most pleasing. Once I started taking lessons with Martin I became more confident. He is a perfectionist therefore will try and push you to become better, giving you the necessary feedback for you to improve. He is an awesome person and you don't feel pressured, ashamed or feel any sort of discomfort driving with him. We occasionally made a few jokes here and there to burn some steam off and always tries to make your driving schedule as comfortable as it can be. Overall I have improved massively from the first lessons with my first instructor to how I am driving now thanks to Martin. 😁 Fully recommend taking lessons with this amazing person.😁"
    let manualphoto6 = 'manualphoto6.jpeg' 
    let manualtext6 =  "I would highly recommend Martin. From the start Martin made sure I was comfortable and ready to drive. He helped establish confidence while driving. He holds the bar high so that when you take your test you are more than ready."
    let autophoto1 = 'autophoto1.jpeg'
    let autotext1 = 'Lucia - 2nd time pass with 4 faults'
    let autophoto2 = 'autophoto2.jpeg'
    let autotext2 = 'Ellie - 1st time pass with 3 faults'
    let autophoto3 = 'autophoto3.jpeg'
    let autotext3 = 'Rachel - 1st time pass with 3 faults'
    let autophoto4 = 'autophoto4.jpeg'
    let autotext4 = 'Andriana - 2nd time pass with 2 faults'
    let autophoto5 = 'autophoto5.jpeg'
    let autotext5 = 'Jake - 1st time pass with 0 faults'
    let autophoto6 = 'autophoto6.jpeg'
    let autotext6 = 'Courtney - 1st time pass with 2 faults'

</script>

{#if activeGearItem == "Manual"}
    <div class="grid-container">
        <div class="Testimonial-1"><TestimonialCard {activeGearItem} photo={manualphoto1} text={manualtext1}/></div>
        <div class="Testimonial-2"><TestimonialCard {activeGearItem} photo={manualphoto2} text={manualtext2}/></div>
        <div class="Testimonial-3"><TestimonialCard {activeGearItem} photo={manualphoto3} text={manualtext3}/></div>
        <div class="Testimonial-4"><TestimonialCard {activeGearItem} photo={manualphoto4} text={manualtext4}/></div>
        <div class="Testimonial-5"><TestimonialCard {activeGearItem} photo={manualphoto5} text={manualtext5}/></div>
        <div class="Testimonial-6"><TestimonialCard {activeGearItem} photo={manualphoto6} text={manualtext6}/></div>
    </div>
{:else if activeGearItem == "Automatic"}
    <div class="grid-container">
        <div class="Testimonial-1"><TestimonialCard {activeGearItem} photo={autophoto1} text={autotext1}/></div>
        <div class="Testimonial-2"><TestimonialCard {activeGearItem} photo={autophoto2} text={autotext2}/></div>
        <div class="Testimonial-3"><TestimonialCard {activeGearItem} photo={autophoto3} text={autotext3}/></div>
        <div class="Testimonial-4"><TestimonialCard {activeGearItem} photo={autophoto4} text={autotext4}/></div>
        <div class="Testimonial-5"><TestimonialCard {activeGearItem} photo={autophoto5} text={autotext5}/></div>
        <div class="Testimonial-6"><TestimonialCard {activeGearItem} photo={autophoto6} text={autotext6}/></div>
    </div>
{/if}

<style>

    .grid-container {
        margin-left: auto;
        margin-right: auto;
        padding-top: 50px;
        justify-content: center;
    }


    @media(min-width:300px) {
        .grid-container {
            width: 250px;
            display: grid;
            grid-template-columns: 1fr;
            grid-template-rows: repeat(6, 1fr);
            gap: 20px 0px;
            grid-template-areas:
            "Testimonial-1"
            "Testimonial-2"
            "Testimonial-3"
            "Testimonial-4"
            "Testimonial-5"
            "Testimonial-6";
        }
    }

    @media(min-width:760px) {
        .grid-container {
            display: grid;
            grid-template-columns: 1fr;
            grid-template-rows: repeat(6, 1fr);
            gap: 20px 0px;
            grid-template-areas:
            "Testimonial-1"
            "Testimonial-2"
            "Testimonial-3"
            "Testimonial-4"
            "Testimonial-5"
            "Testimonial-6";
        }
    }

    @media(min-width:1000px) {
        .grid-container {
            width: 970px;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            grid-template-rows: repeat(3, 1fr);
            gap: 20px 0px;
            grid-template-areas:
                "Testimonial-1 Testimonial-2"
                "Testimonial-3 Testimonial-4"
                "Testimonial-5 Testimonial-6";
        }
    }

    @media(min-width:1220px) {
        .grid-container {
            width: 1200px;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-template-rows: repeat(2, 1fr);
            gap: 20px 20px;
            grid-template-areas:
                "Testimonial-1 Testimonial-2 Testimonial-3"
                "Testimonial-4 Testimonial-5 Testimonial-6";
        }
    }

.Testimonial-1 { grid-area: Testimonial-1; }

.Testimonial-2 { grid-area: Testimonial-2; }

.Testimonial-3 { grid-area: Testimonial-3; }

.Testimonial-4 { grid-area: Testimonial-4; }

.Testimonial-5 { grid-area: Testimonial-5; }

.Testimonial-6 { grid-area: Testimonial-6; }

</style>