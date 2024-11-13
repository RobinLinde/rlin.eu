<nav>
	<slot />
</nav>

<style lang="scss">
	nav {
		// Position the navbar at the top of the screen
		@apply sticky top-0 left-0 w-full h-12 z-10;
		// Position the children at the center of the navigation bar
		@apply flex items-center gap-4 px-6;
		// Border and color
		@apply border-b-2;
		@apply bg-orange-600 border-orange-500 text-white;
		@apply gdark:bg-orange-700 gdark:border-orange-600;
		// Spacing of the items
		@apply justify-between md:justify-start;
		// Hide the navbar on prited pages
		@apply print:hidden;
	}
</style>
