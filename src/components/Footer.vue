<template>
	<footer class="footer-container">
		<p>
			Proudly made with <span class="heart">&#9829;</span> by Marcus Herrera
		</p>
	</footer>
</template>

<style scoped>
.footer-container {
	position: absolute;
	bottom: 0;
	width: 100%;
	color: #001e1d;
	font-weight: bold;
}

.footer-container p {
	width: 250px;
	font-size: 12.38px;
	margin-inline: auto;
}

.footer-container p::before {
	display: block;
	position: absolute;
	top: -200px;
	/* left: 375px; */
	content: '';
	width: 200px;
	height: 600px;
	border-radius: 50%;
	background: radial-gradient(
		circle,
		rgba(0, 124, 121, 1) 0%,
		rgba(0, 70, 67, 1) 100%
	);
	filter: blur(40px);
	transform: rotate(-60deg);
	z-index: -1;
}

.footer-container p::after {
	display: block;
	position: absolute;
	top: -200px;
	/* left: 375px; */
	content: '';
	width: 200px;
	height: 600px;
	border-radius: 50%;
	background: radial-gradient(
		circle,
		rgba(249, 188, 96, 0.3) 0%,
		rgba(0, 70, 67, 1) 100%
	);
	filter: blur(40px);
	transform: rotate(60deg);
	z-index: -2;
}

.heart {
	color: #e16162;
}

@media screen and (max-width: 768px) {
	.footer-container p::before {
		display: block;
		position: absolute;
		top: -130px;
		left: 120px;
		content: '';
		width: 100px;
		height: 300px;
		border-radius: 50%;
		background: radial-gradient(
			circle,
			rgba(0, 124, 121, 1) 0%,
			rgba(0, 70, 67, 1) 100%
		);
		filter: blur(40px);
		transform: rotate(-60deg);
		z-index: -1;
	}

	.footer-container p::after {
		display: block;
		position: absolute;
		top: -130px;
		left: 160px;
		content: '';
		width: 100px;
		height: 300px;
		border-radius: 50%;
		background: radial-gradient(
			circle,
			rgba(249, 188, 96, 0.3) 0%,
			rgba(0, 70, 67, 1) 100%
		);
		filter: blur(40px);
		transform: rotate(60deg);
		z-index: -2;
	}
}
</style>
