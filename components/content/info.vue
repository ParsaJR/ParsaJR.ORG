<template>
	<div class="flex px-4 items-center pl-4 text-sm text-gray-800 gray-300 rounded-lg bg-gray-200 dark:bg-neutral-800 dark:text-gray-300 dark:border-gray-600"
		role="alert">
		<svg class="flex-shrink-0 inline w-4 h-4 me-3" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
			fill="currentColor" viewBox="0 0 20 20">
			<path
				d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5ZM9.5 4a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3ZM12 15H8a1 1 0 0 1 0-2h1v-3H8a1 1 0 0 1 0-2h2a1 1 0 0 1 1 1v4h1a1 1 0 0 1 0 2Z" />
		</svg>
		<span class="sr-only">Info</span>
		<div>
			<slot />
		</div>
	</div>
</template>
