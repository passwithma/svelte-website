<script>

    export let courseVersion;
    export let courseHourly;

</script>

{#if courseVersion === 'Test Booster Course'}
    <div>
        <p>This course includes 15 hours of in car tuition at £{courseHourly} per hour, I usually book your driving test to tie in with the last hour of the course (provided you have passed your theory test).</p>
        <p>The Test Booster Course is ideal for learners who are near test standard and just need a short burst of lessons prior to the test. It is also great for those who have taken a test before or have come up to a test standard in the past but have no had lessons recently.</p>
        <p>The in-car training is 15 hours on a one to one basis (this includes 2 hours for attending the driving test). You need to allocate a further 5 hours to complete home study, bring the total duration of this course to around 20 hours.</p>
    </div>
{:else if courseVersion === 'Midway Pass Course'}
    <div>
        <p>This course includes 20 hours of in car tuition at £{courseHourly} per hour & the driving test fee. I will endeavour to book your driving test to tie in with the last hour of the course (providing you have passed your theory test.</p>
        <p>The course is ideal for those who have already learned the basic control skills of driving. The course can be completed in a week or spread over several depending on your needs and my availability.</p>
        <p>The in-car training is 20 hours on a one to one basis. (This includes 2 hours for attending the driving test).</p>
    </div>
{:else if courseVersion === 'Semi-Intensive Course'}
    <div>
        <p>The course includes 3 hours of in car tuition at £{courseHourly} per hour & the driving test fee. I will endeavour to book your driving test to tie in with the last hour of the course (providing you have passed your theory test).</p>
        <p>The 30 hour semi-intensive course is spread over two or more weeks to suit you and my schedule. This is a very <b>popular and successful</b> form of intensive traning, designed for people who want to pass the test quickly but at a comfortable pace.</p>
        <p>The in-car training is 30 hours on a one to one basis. (this includes 2 hours to attend the test).</p>
    </div>
{:else if courseVersion === 'One Week Pass Course'}
    <div>
        <p>This course includes 30 hours of in car tuition & the driving test fee. I will endeavour to book your driving test to tie in with the last hour of the course (provided you have passed your theory test).</p>
        <p>The One Week Intensive Course generally starts on Sunday or Monday and finishes on Friday. It is ideal for those who are in a hurry, with the driving test usually organized to take place at the end of the week or during the following week of the training depending upon your personal preference. If you want a test at the end of the course you would need to book the course and pass the theory test well in advance of the required start date (due to the COVID situation this might be 2-3 months).</p>
        <p>The in-car training is 30 hours on a one to one basis. (This includes 2 hours to attend the test).</p>
    </div>
{/if}

<style>

</style>