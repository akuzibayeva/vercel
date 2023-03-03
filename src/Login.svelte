<script>
    import { Link, navigate } from 'svelte-navigator'
    import axios from 'axios'

    let usernameInput
    let passwordInput

    const login = async () => {
        let body = {
            username: usernameInput.value,
            password: passwordInput.value
        }

        let response = await axios.post('http://localhost:7070/api/login', body)
        localStorage.setItem('user', JSON.stringify(response.data))
        
    }    
</script>
<div style="font-family: 'Quattrocento Sans', sans-serif;">
    
    <nav class="navbar navbar-expand-lg" style="background-color: white;">
        <div class="container-fluid">
          <!-- svelte-ignore missing-declaration -->
          <Link class="navbar-brand" to="/front/index.html">AURORA</Link>
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
    
<div hscreen flex-col>
    

    <main fill>
        <view-container class="p-10">
            <p class="text-center">Create your personal account to join our Givenchy family</p>
            <div class="input-group">
                <span class="input-group-text">Username and Password</span>
                <input bind:this={usernameInput} type="text" aria-label="Username" class="form-control">
                <input bind:this={passwordInput} type="text" aria-label="Password" class="form-control">
                <button class="btn btn-light" type="button" on:click={login}> Login </button>
            </div>
        </view-container>
        <br>
        <br>
        <Link to="/register" class="text-center">If you are already a Givenchy Family member, please enter your login information.</Link>
        

    </main>
</div>
</div>