<script>

    import PricingDetail from '../components/PricingDetail.svelte';

    export let hourPrice;
    export let activeGearItem;

</script>

<div class="pricing">
    
    <PricingDetail {activeGearItem} {hourPrice}/>

</div>

<style>

    .pricing {
        padding-top: 10px;
        margin-left: auto;
        margin-right: auto;
    }

    @media(min-width:768px) {
        .pricing {
            width: 750px;
        }
    }

    @media(min-width:992px) {
        .pricing {
            width: 970px;
        }
    }

    @media(min-width:1220px) {
        .pricing {
            width: 1200px;
        }
    }

</style>