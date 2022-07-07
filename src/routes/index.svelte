<script lang="ts">
	import TypeWriter from '$lib/components/TypeWriter.svelte';
	import Circle from '$lib/icons/Circle.svelte';

	let speed = 50;
</script>

<div class="content">
	<div class="header">
		<div class="w-6">
			<img alt="logo" src="/images/png/logo.png" class="w-full" />
		</div>
		<div class="font-extrabold">Meta Flash</div>
	</div>
	<div class="middle">
		<div class="middle-content">
			<div class="left">
				<div class="text-4xl text-center md:text-left">Aliqua id fugiat nostrud irure ex</div>
				<div class="text-[#D0D1D2] text-sm leading-5 text-center md:text-left">
					Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis
					deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat
					incididunt sint deserunt ut voluptate aute id deserunt nisi.
				</div>
				<a href="."><button class="button">View on github</button></a>
			</div>
			<div class="right">
				<div class="terminal">
					<div class="top-bar">
						<div class="text-[#FF4444] circle"><Circle /></div>
						<div class="text-[#FFD47A] circle"><Circle /></div>
						<div class="text-[#6DFF46] circle"><Circle /></div>
					</div>
					<div class="terminal-content">
						<div class="text-[#FFE600]">
							<TypeWriter text="# Upload using cURL" {speed} loop />
						</div>
						<div>
							<TypeWriter
								text="$ curl --upload-file ./hello.txt https://transfer.sh/hello.txt https://transfer.sh/Bvdxtp/hello.txt"
								delay={20 * speed}
								{speed}
								loop
							/>
						</div>
						<div class="my-2" />
						<div class="text-[#FFE600]">
							<TypeWriter text="# Using the shell function" delay={120 * speed} {speed} loop />
						</div>
						<div>
							<TypeWriter
								text="$ transfer hello.txt <br />#####################################################<br />
							100.0% https://transfer.sh/QkDtA5/hello.txt"
								delay={150 * speed}
								{speed}
								loop
							/>
						</div>
						<div class="my-2" />
						<div class="text-[#FFE600]">
							<TypeWriter text="# Upload from web" delay={280 * speed} {speed} loop />
						</div>
						<div>
							<TypeWriter
								text="Drag your files here, or click to browse."
								delay={300 * speed}
								{speed}
								loop
							/>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
	<div class="footer">
		<div class="footer-content">
			<div class="text-[#D0D1D2]">© Copyright Meta Flash Loan {new Date().getFullYear()}</div>
			<div class="justify-self-center">Made with ❤️ by <a href=".">Lorem Ipsum</a></div>
		</div>
	</div>
</div>
<div class="bg-image">
	<img src="/images/png/rectangle.png" alt="background" class="image" />
</div>

<style lang="postcss">
	.content {
		@apply relative;
		@apply z-10;
		@apply w-full h-full;
		@apply flex flex-col items-center;
		@apply text-white;
	}

	.header {
		@apply w-full max-w-[80rem];
		@apply bg-[rgba(131,131,131,0.1)];
		@apply flex flex-row items-center gap-4;
		@apply px-14 py-4;
		@apply rounded-b-2xl;
	}

	.middle {
		@apply flex-grow;
		@apply px-6 py-10 md:py-2;
		@apply w-full max-w-[80rem];
		@apply flex flex-col items-center md:justify-center;
	}

	.middle-content {
		@apply w-full;
		@apply flex flex-col items-center md:grid md:grid-cols-2 gap-20;
	}

	.left {
		@apply flex flex-col items-center md:items-start gap-4;
		@apply md:pl-10;
	}

	.button {
		@apply bg-[#4589f7];
		@apply transition-all hover:bg-[#2b75ee];
		@apply rounded-full;
		@apply py-3 px-16;
		@apply text-sm;
	}

	.right {
		@apply w-full;
	}

	.terminal {
		@apply z-[9999];
		@apply rounded-lg;
		@apply bg-[#1E1F22];
		@apply border border-[#333237];
		@apply overflow-hidden;
		@apply text-sm;
		@apply w-full;
	}

	.top-bar {
		@apply bg-[#212225];
		@apply flex flex-row items-center gap-[0.3rem];
		@apply py-2 px-4;
	}

	.circle {
		@apply w-2;
	}

	.terminal-content {
		@apply p-4;
		@apply flex flex-col items-start;
		@apply h-[16rem];
		@apply w-full;
		@apply overflow-auto;
	}

	.terminal-content > div {
		@apply whitespace-normal;
	}

	.footer {
		@apply w-full;
		@apply px-2 py-4 md:px-6 md:py-6;
		@apply bg-[rgba(131,131,131,0.15)];
		@apply text-sm;
		@apply flex items-center justify-center;
	}

	.footer-content {
		@apply w-full max-w-[80rem];
		@apply flex flex-col-reverse gap-2 md:grid grid-cols-3 items-center justify-between;
	}

	a {
		@apply underline;
	}

	.bg-image {
		@apply z-0;
		@apply absolute;
		@apply top-0 left-0;
		@apply h-full w-full;
		@apply overflow-hidden;
		@apply pointer-events-none;
		@apply flex flex-col items-center justify-end;
	}

	.image {
		@apply w-full min-w-[60rem];
		@apply -mb-[40vw];
		@apply blur-[100px];
		@apply opacity-20;
	}
</style>
