<script>

    export let activeGearItem;

</script>


<div class="grid-container">
    <div class="About-LWM">
        <h3>Why learn with <span class="M">M</span>&<span class="A">A</span> Driving School?</h3>
        <p>We are fully qualified Government Approved Driving Instructors (ADI) and we are passionate about road safety. We set ourselves apart from large chain driving schools by providing a bespoke training schedule based around each students individual requirements. These are formulated during the first 2 hours spent with the student and have been shown to increase first time pass rates.</p>
        <p>At M&A we have been specially trained in the latest student-centred learning techniques. When combined with our caring, friendly personalities we help you learn to drive</p>
        <li>Quickly,</li>
        <li>At a pace that suits your needs, and</li>
        <li>In a way that you will look forward to and enjoy every lesson.</li>
        <p>The training systems we use at M&A are formulated around providing flexible and specific training that ensures that you learn to drive safely at a rate that suites you. We aim to make every lesson enjoyable, productive and as relaxing as possible. Lessons are always conducted in a calm, friendly, fun and relaxed manner as we firmly believe in making pupils feel at ease during lessons.</p>
    </div>
    <div class="Blank"></div>
    <div class:hidden={activeGearItem === "Automatic"} class="About">
        <h3>Martin - Manual Driving Instructor</h3>
        <p>My name is Martin and I'm a fully qualified DVSA Driving Instructor.</p>
        <p>I became a driving instructor because I wanted a job with real satisfaction and there is nothing better than seeing someone pass their driving test. I was also told by friends and work colleagues that I was a calm and relaxed type of person and that I would be great at it.</p>
        <p>I was fortunate to be trained by LDC in the latest adult coaching and training techniques so you can be assured the training I give you will be of the highest standard.</p>
        <p>I have lived my life, so far, in Fleet, Farnham & surrounding areas, and now been settled on Elvetham Heath since August 2000. My grandfather used to race Bugatti's and Bentley's at Brooklands and when this ended he became the oldest person to be riding a twin engined BSA drag bike, this is where my love of cars & motorsports began. I've raced many of the circuits around the UK, but my main passion is rallying, I have competed again around the country as a driver.</p>
        <p>Now I use what I've learnt over the years and coupled with the latest coaching techniques, to instruct safe, high standards of driving and instil the responsiblity you must have as a Test Passed Driver.</p>
    </div>
    <div class:hidden={activeGearItem === "Manual"} class="About">
        <h3>Allen - Automatic Driving Instructor</h3>
        <p>My name is Allen and I'm a fully qualified DVSA driving instructor.</p>
        <p>I have lived most of mylife in Farnham and the surrounding areas including Aldershot, Fleet, and Camberley.</p>
        <p>I have always had a passion for motorcycles and cars having owned so many that I've lost count.</p>
        <p>I think this is where my passion to become a driving instructor has come from. Being able to use my lifetime of driving skills to help others become safe and confident drivers.</p>
        <p>I have always felt being an instructor has given me a great deal of satisfaction from helping my pupils in their journey through to becoming a qualified driver. I like to think my patience and relaxed attitude makes for a much easier way of learning to drive.</p>
        <p>My 22 years of teaching has always taught me that we were all learners once and were on the same learning road.</p>
    </div>
    <div class="Areas-Covered">
        <h3>Areas Covered</h3>
        <li>Fleet</li>
        <li>Church Crookham</li>
        <li>Odiham</li>
        <li>Farnborough</li>
        <li>Aldershot</li>
        <li>Farnham</li>
        <li>Yateley</li>
        <li>Sandhurst</li>
        <li>Hook</li>
        <li>Villages surrounding these towns</li>
    </div>
    <div class="padding"></div>
  </div>



<style>

    .hidden {
        display: none;
    }

    .M {
        color: #981E32;
    }

    .A {
        color: #2e75b6;
    }

    * {
        box-sizing: border-box;
    }

    
    li {
        list-style-type: disclosure-closed;
        list-style-position: inside;
    }

    .grid-container {
        margin-left: auto;
        margin-right: auto;
    }


    @media(min-width:768px) {
        .grid-container {
            width: 750px;
            display: grid;
            grid-template-columns: 1fr;
            grid-template-rows: auto;
            gap: 0px 0px;
            grid-template-areas:
                "About-LWM"
                "Areas-Covered"
                "About";
        }
    }

    @media(min-width:992px) {
        .grid-container {
            width: 970px;
            display: grid;
            grid-template-columns: 1fr;
            grid-template-rows: auto;
            gap: 0px 0px;
            grid-template-areas:
                "About-LWM"
                "Areas-Covered"
                "About";
        }
    }

    @media(min-width:1220px) {
        .grid-container {
            width: 1200px;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            grid-template-rows: auto;
            gap: 10px 50px;
            grid-template-areas:
                "About-LWM About-LWM Areas-Covered"
                "Blank About About"
        }
    }
    

    .About-LWM { grid-area: About-LWM; }

    .Areas-Covered { grid-area: Areas-Covered; }

    .About { grid-area: About; }

    .Blank { grid-area: Blank; }

    .padding {
        height: 20px;
    }

</style>