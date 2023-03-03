<script>
    import { Link } from "svelte-navigator"
    import axios from "axios";
    const user = JSON.parse(localStorage.getItem('user'))

    let orders = []

    const fetchOrders = async () => {
        const response = await axios.get('http://localhost:9090/api/order/all', {
            headers: {
                'authorization': user.token
            }
        })

        orders = response.data.orders
    }
    fetchOrders()

</script>

<div style="font-family: 'Quattrocento Sans', sans-serif;">
    <nav class="navbar navbar-expand-lg" style="background-color: white;">
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
      <hr>


      <main fill>
        <view-container hfull flex-col>
            <div between>
                <h2> ORDERS </h2>
            </div>

            <hr mt-10>

            <table class="table">
                <thead>
                    <tr>
                        <th scope="col"> Book Id </th>
                        <th scope="col"> Name </th>
                        <th scope="col"> Owner </th>
                        <th scope="col"> Price </th>
                        <th scope="col"> Count </th>
                        <th scope="col"> Date </th>
                    </tr>
                </thead>
                <!-- svelte-ignore missing-declaration -->
                {#each orders as order }   
                    <tr>
                        <td> {order.id} </td>
                        <td> {order.name} </td>
                        <td> {order.user}</td>
                        <td> {order.price} </td>
                        <td> {order.count} </td>
                        <td> {order.date} </td>
                    </tr>
                {/each}
            </table>
           
        </view-container>
    </main>
      <p class="fs-1 text-center">GIVENCHY</p>
</div>
