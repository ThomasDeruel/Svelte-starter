<script>
  import { Router, Route, Link } from "svelte-routing";
  import Home from "./routes/Home.svelte";
  import About from "./routes/About.svelte";
  export let url = ""; //This property is necessary declare to avoid ignore the Router
</script>


<Router url="{url}">
 <nav>
    <Link to="/">Home</Link>
    <Link to="about">About</Link>
  </nav>
  <div>
	<Route path="/about"><About pageName="About me" /></Route>
    <!--<Route path="about" component="{Else}" /> -->
    <!--for now the router just support case sensitive,
        one workaround could be add two time the route
        Example.
       <Route path="About" component="{About}" /> 
    -->
    <Route path="/"><Home pageName="Home Page" /></Route>
  </div>
</Router>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>