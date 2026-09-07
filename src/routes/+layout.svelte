<script>
	import './layout.css';
	import "@fontsource-variable/inter/wght.css";
	import "@fontsource-variable/montserrat/wght.css"

	import favicon from '$lib/assets/favicon.png';
	import Icon from '@iconify/svelte';
	import userProfile from '$lib/assets/userProfile.webp'
	import Footer from '$lib/components/Footer.svelte'

	import { onMount } from "svelte";
	import { themeChange } from "theme-change";
  	import { goto } from '$app/navigation';

	const themes = [
		"garden", "dracula", "dim", "sunset", "autumn", "luxury", "silk",
	]

	// Testing values
	const displayName = "Nez"
	const email = "nezissogated@vilvisoftware.net"

	let { children } = $props();
	onMount(() => {
		themeChange(false)
		goto('/dashboard')
	})
</script>

<div class="app-layout drawer lg:drawer-open">
	<input type="checkbox" id="drawer-4" class="drawer-toggle inline" />
	<div class="drawer-content">
		<header>
			<nav class="navbar">
				<label for="drawer-4" aria-label="open sidebar" class="btn btn-square btn-ghost drawer-button">
					<Icon icon="material-symbols:menu-rounded" class="w-5 h-5" />
				</label>
				<div class="flex-1">
					<h1><a class="btn btn-ghost text-lg" href="/dashboard">Sprig</a></h1>
				</div>
				<div class="flex-none">
					<ul class="menu menu-horizontal px-1">
						<li>
							<details class="dropdown dropdown-end">
								<summary>
									<div class="avatar mr-3">
										<div class="ring-primary ring-offset-base-100 rounded-full w-9 ring-2 ring-offset-2">
											<img src={userProfile} alt="User's profile picture." />
										</div>
									</div>
									{displayName}
								</summary>
								<ul class="menu dropdown-content bg-base-100 shadow-md max-w-90 z-1 gap-2">
								
									<li>
										<div class="flex flex-row items-center justify-center">
											<div class="flex flex-row items-center">
												<div class="avatar mr-3">
													<div class="ring-primary ring-offset-base-100 rounded-full w-9 ring-2 ring-offset-2">
														<img src={userProfile} alt="pfp" />
													</div>
												</div>
												<div class="flex flex-col items-start">
													<h2>{displayName}</h2>
													<p class="text-xs opacity-60">{email}</p>
												</div>
											</div>
										</div>
									</li>
									<li><button><Icon icon="material-symbols:person" class="w-5 h-5"/>Switch account</button></li>
									<li><button class="text-error"><Icon icon="material-symbols:exit-to-app-rounded" class="w-5 h-5"/>Leave</button></li>
								</ul>
							</details>
						</li>
					</ul>
				</div>
			</nav>
		</header>

		<!-- Main content goes here yay :3 -->
		<main class="p-3">
			{@render children()}
		</main>

		<Footer />
	</div>

	<div class="drawer-side is-drawer-close:overflow-visible">
		<label for="drawer-4" aria-label="close sidebar" class="drawer-overlay"></label>
		<div class="flex min-h-full flex-col items-start bg-base-200 is-drawer-close:w-14 is-drawer-open:w-64">

			<!-- sidebarcontent -->
			<ul class="menu w-full grow justify-center gap-3 flex-1">
				<li>
					<a class="is-drawer-close:tooltip is-drawer-close:tooltip-right" data-tip="Dashboard" href="/dashboard">
						<Icon icon="material-symbols:home-rounded" class="w-5 h-5" />
						<span class="is-drawer-close:hidden">Dashboard</span>
					</a>
				</li>
				<li>
					<a class="is-drawer-close:tooltip is-drawer-close:tooltip-right" data-tip="Categories" href="/categories">
						<Icon icon="material-symbols:label" class="w-5 h-5" />
						<span class="is-drawer-close:hidden">Categories</span>
					</a>
				</li>
				<li>
					<a class="is-drawer-close:tooltip is-drawer-close:tooltip-right" data-tip="Budgets" href="/budgets">
						<Icon icon="material-symbols:universal-currency-alt-rounded" class="w-5 h-5" />
						<span class="is-drawer-close:hidden">Budgets</span>
					</a>
				</li>
				<li>
					<a class="is-drawer-close:tooltip is-drawer-close:tooltip-right" data-tip="Expenses" href="/expenses">
						<Icon icon="material-symbols:shopping-bag" class="w-5 h-5" />
						<span class="is-drawer-close:hidden">Expenses</span>
					</a>
				</li>
			</ul>
			<ul class="menu w-full grow justify-center gap-3 flex-2">
				<li>
					<a class="is-drawer-close:tooltip is-drawer-close:tooltip-right" data-tip="Settings" href="/settings">
						<Icon icon="material-symbols:settings" class="w-5 h-5" />
						<span class="is-drawer-close:hidden">Settings</span>
					</a>
				</li>
				<li>
					<fieldset class="fieldset is-drawer-close:hidden">
						<legend class="fieldset-legend">
							<Icon icon="material-symbols:palette" class="w-5 h-5" />
							Themes
						</legend>
						<select class="is-drawer-close:hidden is-drawer-close:tooltip-right select" data-tip="Themes">
							{#each themes as theme}
								<option data-set-theme={theme}>{theme.toLocaleUpperCase()}</option>
							{/each}
						</select>
					</fieldset>
				</li>
			</ul>
		</div>
	</div>

</div>

<style>
	:global(body) {
		margin: 0;
		font-family: "Inter Variable", sans-serif;
	}

	:global(h1) {
		font-family: "Montserrat Variable", sans-serif;
	}
</style>

<svelte:head>
	<title>Sprigate</title>
	<link rel="icon" href={favicon} />
</svelte:head>

