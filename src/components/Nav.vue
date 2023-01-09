<template>
	<div class="nav-container">
		<img
			src="../assets/views-logo-transparent.svg"
			alt="Views logo"
			class="nav-logo"
		/>
		<div class="nav-links">
			<a
				href="https://github.com/mahiv87/Views-by-Vue"
				class="nav-button"
				target="_blank"
				>GitHub</a
			>
			<a href="#" class="nav-button" target="_blank">Donate</a>
		</div>
	</div>
</template>

<style scoped>
.nav-container {
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	padding: 0px 25px;
	/* gap: 350px; */
	background: #001e1d;
	height: 70px;
}

.nav-logo {
	position: relative;
	top: 33px;
	width: 150px;
	height: auto;
}

.nav-links {
	display: flex;
	flex-direction: row;
	align-items: center;
	padding: 0px;
	gap: 36px;
	width: 274px;
	height: 47px;
}

.nav-button {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	gap: 10px;
	width: 75px;
	height: 25px;
	border-radius: 30px;
	color: #fffffe;
	font-weight: bold;
	text-decoration: none;
}

.nav-button:hover {
	background: #e8e4e6;
	color: #001e1d;
	transition: all ease 500ms;
}
</style>
