<script>
   import { Link, navigate } from 'svelte-navigator'
    import axios from 'axios'

    let usernameInput
    let passwordInput
    let nameInput
    let surnameInput

    const register = async () => {
        let body = {
            name: nameInput.value,
            surname: surnameInput.value,
            username: usernameInput.value,
            password: passwordInput.value
        }
        let response = await axios.post('http://localhost:7070/api/register', body)
        localStorage.setItem('user', JSON.stringify(response.data))
    }  
</script>

<div>
    <nav class="navbar navbar-expand-lg" style="background-color: #white;">
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
    
 <div>
      <h3 class="text-center"> Register </h3>
            <input class="form-control" bind:this={usernameInput} placeholder="Username" type="text">
            <input class="form-control" bind:this={passwordInput} placeholder="Password" type="text">
            <input class="form-control" bind:this={nameInput} placeholder="Name" type="text">
            <input class="form-control" bind:this={surnameInput} placeholder="Surname" type="text"> <br>
            <button class="btn btn-dark d-grid gap-2 col-1 mx-auto" on:click={register}> Register </button> <br>

      <Link to="/login" class=" btn d-grid gap-2 col-1 mx-auto"> Back to Login </Link>
</div>
</div>    