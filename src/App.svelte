<script>
	import { Router, Route } from 'svelte-navigator'
    import Index from './Index.svelte';
    import Women from './Women.svelte'
    import Men from './Men.svelte'
    import Orders from './Orders.svelte';
    import Login from './Login.svelte';
    import Register from './Register.svelte';
</script>

<Router>
    <Route path="/">
        <Index/>
    </Route>
    <Route path="/women">
        <Women/>
    </Route>
    <Route path="/men">
        <Men/>
    </Route>
    <Route path="/orders">
        <Orders/>
    </Route>
    <Route path="/login">
        <Login/>
    </Route>
    <Route path="/register">
        <Register/>
    </Route>
</Router>