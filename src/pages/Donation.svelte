<script>
  import { onMount } from "svelte";
  import Header from '../component/Header.svelte';
  import Footer from '../component/Footer.svelte';
  

  export let params;
  let charity;
  

  async function getCharity(id){
    const res = await fetch('https://charity-api-bwa.herokuapp.com/charities/${id}')
    return res,json();
  }

  
  onMount(async function(){
    charity= await getCharity(params.id);
  });


</script>

<Header/>
<!-- welcome section -->
    <!--breadcumb start here-->
    {#if charity}
    <section class="xs-banner-inner-section parallax-window" style=
    "background-image:url('/assets/images/backgrounds/kat-yukawa-K0E6E0a0R3A-unsplash.jpg')">
      <div class="xs-black-overlay"></div>
      <div class="container">
        <div class="color-white xs-inner-banner-content">
          <h2>Donate Now</h2>
          <p>{charity.title}</p>
          <ul class="xs-breadcumb">
            <li class="badge badge-pill badge-primary">
              <a href="/" class="color-white">Home /</a> Donate
            </li>
          </ul>
        </div>
      </div>
    </section><!--breadcumb end here--><!-- End welcome section -->
    <main class="xs-main">
      <!-- donation form section -->
      <section class="xs-section-padding bg-gray">
        <div class="container">
          <div class="row">
            <div class="col-lg-6">
              <div class="xs-donation-form-images"><img src=
              "/assets/images/christian-dubovan-Y_x747Yshlw-unsplash.jpg" class="img-responsive" alt=
              "Family Images"></div>
            </div>
            <div class="col-lg-6">
              <div class="xs-donation-form-wraper">
                <div class="xs-heading xs-mb-30">
                  <h2 class="xs-title">{charity.title}</h2>
                  <p class="small">To learn more about make donate charity
                    with us visit our "<span class="color-green">Contact
                      us</span>" site. By calling <span class=
                      "color-green">+44(0) 800 883 8450</span>.</p><span class=
                      "xs-separetor v2"></span>
                </div><!-- .xs-heading end -->
                <form action="#" method="post" id="xs-donation-form" class=
                "xs-donation-form" name="xs-donation-form">
                  <div class="xs-input-group">
                    <label for="xs-donate-name">Donation Amount <span class=
                    "color-light-red">**</span></label> <input type="text"
                    name="name" id="xs-donate-name" class="form-control"
                                                                                               placeholder="Minimum of $5">
                  </div><!-- .xs-input-Yourname -->
                  <div class="form-group">
                    <label for="exampleInputName">Your name
                    <span class="color-light-red">**</span>
                    </label>
                    <input required type="text" class="form-control" id="exampleInputName"
                      aria-describedby="nameHelp" placeholder="Enter full name">
                  </div><!-- .xs-input-your email -->
                  <div class="form-group">
                    <label for="exampleInputEmail1">Email address
                    <span class="color-light-red">**</span>
                    </label>
                    <input required type="email" class="form-control" id="exampleInputEmail1"
                      aria-describedby="emailHelp" placeholder="Enter email">
                  </div>
                  <!-- .xs-input-group END 
                  <div class="xs-input-group">
                    <label for="xs-donate-charity">List of Evaluated Charities
                    <span class="color-light-red">**</span></label>
                    <select name="charity-name" id="xs-donate-charity" class=
                    "form-control">
                      <option value="">
                      Select
                      </option>
                      <option value="amarokSocity">
                      Amarok socity
                      </option>
                      <option value="amarokSocity">
                      Amarok socity
                      </option>
                      <option value="amarokSocity">
                      Amarok socity
                      </option>
                      <option value="amarokSocity">
                      Amarok socity
                      </option>
                    </select>
                  </div>-->
                  <div class="form-check">
                    <input type="checkbox" class="form-check-input" id="exampleCheck1">
                    <label class="form-check-label" for="exampleCheck1">I Agree</label>
                  </div>
                  <!-- .xs-input-group END -->
                  <button type="submit" class="btn btn-warning"><span class=
                  "badge"><i class="fa fa-heart"></i></span> Donate
                now</button>
                </form>
                <!-- .xs-donation-form #xs-donation-form END -->
              </div>
            </div>
          </div><!-- .row end -->
        </div><!-- .container end -->
      </section><!-- End donation form section -->
    </main>
    {/if}
    <Footer/>