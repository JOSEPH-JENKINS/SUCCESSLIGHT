<script>
	export let title;
	
	let opened = false;
	let color = "black";

	const toggleMenu = () =>{
		opened = !opened;
		if (color == "black") {
			color = "white";
		} else {
			color = "black"
		}
	}
</script>

<nav>
	<div class="header">
		<header>
			<div class="logo">
				<h1>{title}</h1>
			</div>
			<nav>
				<ul>
					<li><a href="/">Home</a></li>
					<li><a href="/">about us</a></li>
					<li><a href="/">our services</a></li>
					<li><a href="/">contact us</a></li>
				</ul>
			</nav>
			<div class="menu" on:click={toggleMenu}>
				<div class="menu-lines">
					<div class="line" style="background: {color}"></div>
					<div class="line" style="background: {color}"></div>
					<div class="line" style="background: {color}"></div>
				</div>
			</div>
		</header>
	</div>
	{#if opened}
		<div class="menudropdown">
			<div class="links">
				<div class="link">
					<a href="/"><h1>Home</h1></a>
				</div>
				<div class="link">
					<a href="/"><h1>About</h1></a>
				</div>
				<div class="link">
					<a href="/"><h1>Services</h1></a>
				</div>
				<div class="link">
					<a href="/"><h1>Contact</h1></a>
				</div>
			</div>
			<div class="social-links">
				<div class="socials">
					<div class="facebook">
						<a href="/">FB</a>
					</div>
					<div class="facebook">
						<a href="/">IG</a>
					</div>
					<div class="facebook">
						<a href="/">TW</a>
					</div>
				</div>
			</div>
		</div>
	{/if}
</nav>

<style>
	.header{
		width: 100%;
		padding: 10px;
		border-bottom: 1px solid black;
	}
	header{
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.logo h1{
		font-size: 1.33vw;
	}
	nav{
		width: 65%;
		height: 100%;
	}
	ul{
		padding: 0px 20px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		list-style: none;
	}
	li{
		color: black;
		text-transform: uppercase;
		font-weight: bold;
		flex: 1;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	li a:hover{
		border: 1px solid black;
		padding: 5px 10px;
		border-radius: 20px;
		transition: all .25s ease-in-out;
	}
	.menu{
		display: none;
		height: 40px;
		width: 60px;
		padding: 10px;
		z-index: 999;
	}
	.menu-lines{
		height: 100%;
		width: 100%;
		display: flex;
		justify-content: space-between;
		align-items: flex-end;
		flex-direction: column;
	}
	.line{
		width: 100%;
		height: 1.8056px;
		background-color: black;
	}
	.line:nth-child(2){
		width: 80%;
	}
	.line:nth-child(3){
		width: 60%;
	}
	.menudropdown{
		height: 100vh;
		width: 70%;
		position: absolute;
		top: 0;
		right: 0;
		background: #121212;
		color: white;
		padding: 20px;
		transition: all .25s ease;
	}
	@media (max-width: 500px){
		nav{
			display: none;
		}
		.logo{
			width: 50%;
		}
		.logo h1{
			font-size: 4.133vw;
		}
		.menu,
		.menudropdown{
			display: block;
		}
	}
	@media (max-width: 900px) and (min-width: 500px){
		nav{
			display: none;
		}
		.logo h1{
			font-size: 2.333vw;
		}
		.menu,
		.menudropdown{
			display: block;
		}
		.menudropdown{
			width: 40%;
		}
	}
</style>