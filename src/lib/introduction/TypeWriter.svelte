<script>
	let phraseIndex = 0;

	let phrases = ['Hello, World!', 'Labas, Pasauli!', 'Hallo, Welt!', '안녕하세요, 세상아!'];
	let phrase = phrases[phraseIndex];
	let breakpoint = 7;

	let typedHello = '';
	let typedWorld = '';
	let index = 0;
	let typewriter;

	let typeSpeed = 100;

	function typeChar() {
		if (index < phrase.length) {
			if (index < breakpoint) {
				typedHello += phrase[index];
			} else {
				typedWorld += phrase[index];
			}
			index += 1;
		} else {
			stopTyping();
		}
	}

	function deleteChar() {
		if (index > 0) {
			if (index >= breakpoint) {
				typedWorld = typedWorld.slice(0, -1);
			} else {
				typedHello = typedHello.slice(0, -1);
			}
			index -= 1;
		} else {
			typedHello = '';
			stopDeleting();
			phraseIndex += 1;
			phrase = phrases[phraseIndex % phrases.length];
		}
	}
	function startTyping() {
		typewriter = setInterval(typeChar, typeSpeed);
	}

	function startDeleting() {
		typewriter = setInterval(deleteChar, typeSpeed);
	}
	function stopTyping() {
		clearInterval(typewriter);
		setTimeout(startDeleting, 2000);
	}
	function stopDeleting() {
		clearInterval(typewriter);
		setTimeout(startTyping, 500);
	}

	startTyping();
</script>

<div class="container">
	<h1 class="typewriter">
		<span class="typewriter">
			{typedHello}
			<span style="color: var(--main-color)">{typedWorld}</span>
		</span>
	</h1>
</div>

<style>
	@media only screen and (max-width: 25rem) {
		h1 {
			font-size: 1.4rem;
		}
	}
	.typewriter {
		border-right: 0.15rem solid var(--main-color); /* Adds a cursor effect */
		white-space: nowrap; /* Keeps the text in a single line */
		animation: blink-caret 0.75s step-end infinite;
	}

	.container {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	@keyframes blink-caret {
		from,
		to {
			border-color: transparent;
		}
		50% {
			border-color: var(--main-color);
		}
	}
</style>
