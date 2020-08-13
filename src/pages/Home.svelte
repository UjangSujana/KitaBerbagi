<script>
    import { onMount } from 'svelte';
    import KitaBerbagi from "../component/KitaBerbagi.svelte";
    import Header from '../component/Header.svelte';
    import Wellcome from '../component/Wellcome.svelte';
    import Promo from '../component/Promo.svelte';
    import Footer from '../component/Footer.svelte';

    
    let title ="charity";
    let charities = [];

    onMount(async function() {
        const res = await fetch('https://charity-api-bwa.herokuapp.com/charities');
        charities = await res.json()
    }) 

</script>



<Header />
<Wellcome />
<KitaBerbagi {charities} />
<Promo />
<Footer />
