        
<template>
  <div id="app">
    <!-- Pushy Menu -->
    <aside class="pushy pushy-right">
      <div class="cart-content">
        <div class="clearfix">
          <a href="javascript:void(0)" class="pushy-link text-white-gray">Close</a>
        </div>
        <ul class="list-unstyled">
          <li class="clearfix">
            <a href="#" class="float-left">
              <img src="images/shop/p1.jpg" class="img-fluid" alt="" width="60">
            </a>
            <div class="oHidden">
              <span class="close"><i class="ti-close"></i></span>
              <h4><a href="#">Men's Special Watch</a></h4>
              <p class="text-white-gray"><strong>$299.00</strong> x 1</p>
            </div>
          </li><!--/cart item-->
          <li class="clearfix">
            <a href="#" class="float-left">
              <img src="images/shop/p2.jpg" class="img-fluid" alt="" width="60">
            </a>
            <div class="oHidden">
              <span class="close"><i class="ti-close"></i></span>
              <h4><a href="#">Men's tour beg</a></h4>
              <p class="text-white-gray"><strong>$99.00</strong> x 1</p>
            </div>
          </li><!--/cart item-->
          <li class="clearfix">
            <a href="#" class="float-left">
              <img src="images/shop/p3.jpg" class="img-fluid" alt="" width="60">
            </a>
            <div class="oHidden">
              <span class="close"><i class="ti-close"></i></span>
              <h4><a href="#">Women's T-shirts</a></h4>
              <p class="text-white-gray"><strong>$199.00</strong> x 1</p>
            </div>
          </li><!--/cart item-->
          <li class="clearfix">

            <div class="float-right">
              <a href="#" class="btn btn-primary">Checkout</a>
            </div>
            <h4  class="text-white">
              <small>Subtotal - </small> $49.99
            </h4>
          </li><!--/cart item-->
        </ul>
      </div>
    </aside>
    <!-- Site Overlay -->
    <div class="site-overlay"></div>

    <nav class="navbar navbar-expand-lg navbar-light navbar-color navbar-transparent-light nav-sticky">
      <div class="search-inline">
        <form>
          <input type="text" class="form-control" placeholder="Type and hit enter...">
          <button type="submit"><i class="ti-search"></i></button>
          <a href="javascript:void(0)" class="search-close"><i class="ti-close"></i></a>
        </form>
      </div>
      <div class="container">

        <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <router-link class="navbar-brand" to="/"><img src="/images/diet.png" alt=""></router-link>
        <div  id="navbarNavDropdown" class="navbar-collapse collapse">
          <ul class="navbar-nav ml-auto">
            <li class="nav-item dropdown">
              <a class="nav-link  dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false" href="#">Pages</a>
              <ul class="dropdown-menu dropdown-menu-right">
                <li><router-link to="/" class="dropdown-item">Home</router-link></li>
              </ul>
            </li>

          </ul>        
        </div>


      </div>
    </nav>

    <vue-particles
      class="particles-top"
      color="#FFFFFF"
      :particleOpacity="0.7"
      :particlesNumber="120"
      shapeType="circle"
      :particleSize="6"
      linesColor="#E0E0E0"
      :linesWidth="1"
      :lineLinked="true"
      :lineOpacity="0.4"
      :linesDistance="150"
      :moveSpeed="3"
      :hoverEffect="true"
      hoverMode="grab"
      :clickEffect="true"
      clickMode="push"
    >
    </vue-particles>

    <div class="container mb-3">
      <router-view/>
    </div>

      <footer class="footer footer-standard pt50 pb10">
        <div class="container">
          <div class="row">
            <div class="col-lg-4 col-md-6 mb40">
              <h3>Why eat well?</h3>
              <p>
                We've all heard it before, but it's true: eating well is really good for you. When you eat a well-balanced diet:
                your energy levels will be optimised,
                you’ll feel healthier and stronger,
                your immune system will be tougher,
                you’ll think more clearly and handle stress better,
                your chances of developing diabetes, cancer and cardiovascular disease will decrease
              </p>
              <a href="#" class="btn btn-white-outline btn-sm">A Healthy Outside Starts from the Inside</a>
            </div>
            <div class="col-lg-2 col-md-6 mb40">
              <h3>Quick links</h3>
              <ul class="list-unstyled footer-list-item">
                <li>
                  <a href="#">
                    About
                  </a>
                </li>
                <li>
                  <a href="#">
                   News
                 </a>
               </li>
               <li>
                <a href="#">
                 FAQS
               </a>
             </li>
             <li>
              <a href="#">
               Contact
             </a>
           </li>
           <li>
            <a href="#">
              Term & conditions
            </a>
          </li>

        </ul>
      </div>
      <div class="col-lg-3 col-md-6 mb40">
        <h3>Choose Health</h3>
        <ul class="list-unstyled latest-news">
          <li class="media">
           <a href="#"> <img class="d-flex mr-3 img-fluid" width="64" src="images/img1.jpg" alt="Generic placeholder image"></a>
           <div class="media-body">
            <h5 class="mt-0 mb-1"><a href="#">Eat Smarter</a></h5>
            November 14, 2019
          </div>
        </li>
        <li class="media my-3">
          <a href="#"> <img class="d-flex mr-3 img-fluid" width="64" src="images/img2.jpg" alt="Generic placeholder image"></a>
          <div class="media-body">
            <h5 class="mt-0 mb-1"><a href="#">Healthy Food Facts</a></h5>
            Jan 05, 2019
          </div>
        </li>
        <li class="media">
          <a href="#"> <img class="d-flex mr-3 img-fluid" width="64" src="images/img5.jpg" alt="Generic placeholder image"></a>
          <div class="media-body">
            <h5 class="mt-0 mb-1"><a href="#">Health requires healthy food</a></h5>
            March 15, 2019
          </div>
        </li>
      </ul>
    </div>
    <div class="col-lg-3 col-md-6 mb40">
      <h3>Make the right choices</h3>
      <img src="images/map-img.png" alt="" class="img-fluid">
    </div>
    </div>
    </div>
    </footer><!--/footer-->
    <div class="footer-bottomAlt">
      <div class="container">
        <div class="row">
          <div class="col-lg-7">
            <div class="clearfix">
              <a href="#" class="social-icon-sm si-dark si-facebook si-dark-round">
                <i class="fa fa-facebook"></i>
                <i class="fa fa-facebook"></i>
              </a>
              <a href="#" class="social-icon-sm si-dark si-twitter si-dark-round">
                <i class="fa fa-twitter"></i>
                <i class="fa fa-twitter"></i>
              </a>
              <a href="#" class="social-icon-sm si-dark si-g-plus si-dark-round">
                <i class="fa fa-google-plus"></i>
                <i class="fa fa-google-plus"></i>
              </a>
              <a href="#" class="social-icon-sm si-dark si-skype si-dark-round">
                <i class="fa fa-skype"></i>
                <i class="fa fa-skype"></i>
              </a>
              <a href="#" class="social-icon-sm si-dark si-linkedin si-dark-round">
                <i class="fa fa-linkedin"></i>
                <i class="fa fa-linkedin"></i>
              </a>  
            </div>
          </div>
          <div class="col-lg-5">
            <span>&copy; Copyright 2019. All Right Reserved</span>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<style>
body {
  /*font-family: "Book Antiqua", Palatino, "Palatino Linotype", "Palatino LT STD", Georgia, serif;*/
  font-family: "Lucida Bright", Georgia, serif; font-size: 24px;
  background-image: url('/images/background.jpeg'); 
  background-position: center;
  background-repeat: repeat;
  background-size: cover
  /*max-width: 100% !important;
  padding: 0px !important;*/
}

.particles-top {
  /* Permalink - use to edit and share this gradient: https://colorzilla.com/gradient-editor/#b4e391+0,61c419+53,61c419+53,61c419+100&1+0,1+81,0+100 */
  background: -moz-linear-gradient(top,  rgba(180,227,145,1) 0%, rgba(97,196,25,1) 53%, rgba(97,196,25,1) 81%, rgba(97,196,25,0) 100%); /* FF3.6-15 */
  background: -webkit-linear-gradient(top,  rgba(180,227,145,1) 0%,rgba(97,196,25,1) 53%,rgba(97,196,25,1) 81%,rgba(97,196,25,0) 100%); /* Chrome10-25,Safari5.1-6 */
  background: linear-gradient(to bottom,  rgba(180,227,145,1) 0%,rgba(97,196,25,1) 53%,rgba(97,196,25,1) 81%,rgba(97,196,25,0) 100%); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#b4e391', endColorstr='#0061c419',GradientType=0 ); /* IE6-9 */


  padding:0px;

}
</style>


<script>
export default {
  mounted: function() {
    setTimeout(function() {
      var canvas = document.querySelector("#particles-js canvas");
      canvas.height = "600";
      console.log(canvas);
    }, 25);
  }
}
</script>


