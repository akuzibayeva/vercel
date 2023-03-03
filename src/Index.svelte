<script>
	import { Link } from 'svelte-navigator'
</script>

<div style="font-family: 'Quattrocento Sans', sans-serif;">
  <nav class="navbar navbar-expand-lg" style="background-color: #C1A8A6;">
    <div class="container-fluid">
      <!-- svelte-ignore missing-declaration -->
      <Link class="navbar-brand" to="/">AURORA</Link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <!-- svelte-ignore missing-declaration -->
            <Link class="nav-link active" aria-current="page" to="/women">WOMEN</Link>
          </li>
          <li class="nav-item">
            <!-- svelte-ignore missing-declaration -->
            <Link class="nav-link active" aria-current="page" to="/men">MEN</Link>
          </li>

          <li class="nav-item">
            <!-- svelte-ignore missing-declaration -->
            <Link class="nav-link active" aria-current="page" to="/orders">BAG</Link>
          </li>
          <li class="nav-item">
            <!-- svelte-ignore missing-declaration -->
            <Link class="nav-link active" aria-current="page" to="/login">SING IN</Link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

      <div style="background-color: #C1A8A6;">
        <p style="display: flex; justify-content: center;">New In: The Voyou Bag <br>
            FOR HER DISCOVER MORE</p>
                <hr>
                <!-- svelte-ignore missing-declaration -->
        <Link to="/women"><img src="https://www.givenchy.com/coremedia/resource/blob/871932/aa538cbd3e93953789e415ebf531a97d/campaign-wss23-gigi-2-45-data.jpg" alt="" style="width: 100%;"></Link>
    </div>
    
    <div style="background-color: #ccc;">
        <br>
        <p style="display: flex; justify-content: center;">Givenchy Iconics <br>
            ICONICS BOOTS FOR HER</p>
                <!-- svelte-ignore missing-declaration -->
        <!-- svelte-ignore a11y-missing-attribute -->
        <Link to="/women"><img src="https://www.givenchy.com/coremedia/resource/blob/894356/5c3f2b68713aff243a58390215d24348/mktg-spring-anckle-pink-45-data.jpg" style="margin-left: 10%; margin-right:10%"></Link>
        <br> <br> <br> <br> 
    </div>
        
    <div style="background-color: #fffff;">
        <br> <br> <br> <br>
        <p style="display: flex; justify-content: center;">Spring Summer 2023 Collection <br>
            FOR HIM</p> <br>
            <!-- svelte-ignore missing-declaration -->
        <Link to="/men"><img src="https://www.givenchy.com/coremedia/resource/blob/894362/5a0e9294ae670e482d6aa4720fa5a906/backstage-ss23-men-1002-data.jpg" alt="" style="margin-left: 10%; margin-right:10%"></Link>
    </div>
</div>