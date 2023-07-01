<script lang="ts">
	let phraseIndex = 0;

	let phrases = [
		{ phrase: 'Hello, World!', breakpoint: 7 },
		{ phrase: 'Labas, Pasaulis!', breakpoint: 7 },
		{ phrase: 'Hallo, Welt!', breakpoint: 7 },
		{ phrase: '안녕하세요, 세상아!', breakpoint: 7 }
	];
	let phrase = phrases[phraseIndex % phrases.length]['phrase'];
	let breakpoint = phrases[phraseIndex % phrases.length]['breakpoint'];

	let typedHello = '';
	let typedWorld = '';
	let index = 0;
	let typewriter: number; // for setInterval/clearInterval

	const typeChar = () => {
		if (index < phrase.length) {
			if (index < breakpoint) {
				typedHello += phrase[index];
			} else {
				typedWorld += phrase[index];
			}
			index += 1;
		} else {
			stopTyping();
			return;
		}
	};

	const deleteChar = () => {
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
			phrase = phrases[phraseIndex % phrases.length]['phrase'];
			breakpoint = phrases[phraseIndex % phrases.length]['breakpoint'];
			return;
		}
	};

	const typing = () => (typewriter = setInterval(typeChar, 100));
	const deleting = () => (typewriter = setInterval(deleteChar, 100));

	const stopTyping = () => {
		clearInterval(typewriter);
	};
	const stopDeleting = () => {
		clearInterval(typewriter);
	};

	typing();
	setTimeout(() => {
		deleting();
	}, 4000);

	setInterval(() => {
		typing();
		setTimeout(() => {
			deleting();
		}, 4000);
	}, 6000);
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
