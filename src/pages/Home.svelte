<script>
    import KitaBerbagi from "../component/KitaBerbagi.svelte";
    import Header from '../component/Header.svelte';
    import Wellcome from '../component/Wellcome.svelte';
    import Promo from '../component/Promo.svelte';
    import Footer from '../component/Footer.svelte';

    import {charities} from "../Data/charities.js" ;

    let title ="Kita Berbagi";
</script>



<Header />
<Wellcome />
<KitaBerbagi {charities} />
<Promo />
<Footer />
