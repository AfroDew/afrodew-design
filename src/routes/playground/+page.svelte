<script lang="ts">
	const menuList = [
		{ path: '#dashboard', icon: '#', name: 'Dashoard' },
		{ path: '#post', icon: '#', name: 'Post' },
		{ path: '#homes', icon: '#', name: 'Homes' },
		{ path: '#business', icon: '#', name: 'Business' },
		{ path: '#dispatch', icon: '#', name: 'Dispatch' }
	];

	const newActions = [
		{ name: 'Post' },
		{ name: 'Home' },
		{ name: 'Business' },
		{ name: 'Dispatch' }
	];
</script>

<main>
	<div class="appbar">
		<!-- Account Zone -->
		<div class="account-zone">
			<div class="avatar">
				<img class="icon" src="/img/profile.jpg" alt="User looks" />
			</div>
			<div>
				<span class="greeting">Good Day</span>
				<span class="name">Siki Iniworikabo-Oforie</span>
			</div>
		</div>

		<!-- Menu -->
		<div class="menu">
			<span>Menu</span>
			<ul>
				{#each menuList as item}
					<li>
						<a href={item.path}>
							<img class="icon" src={item.icon} alt={''} />
							<span>{item.name}</span>
						</a>
					</li>
				{/each}
			</ul>
		</div>

		<!-- Notifications -->
		<div class="notifications">
			<!-- List -->
			Notifications
		</div>

		<!-- New Actions -->
		<div class="new-actions">
			{#each newActions as { name }}
				<button>
					<div class="plus-icon" />
					<span>{name}</span>
				</button>
			{/each}
		</div>
	</div>
</main>

<style>
	*,
	::before,
	::after {
		box-sizing: border-box;
	}

	main {
		background-image: url('/img/bg.avif');
		background-size: contain;
		width: 100vw;
		min-height: 100vh;
		color: #fff;
	}

	.appbar {
		width: 100vw;
		height: 100vh;
		transition: background 0.6s ease;
		border-bottom: 1px solid #eaeaea;
		transform: translateZ(0);
		backdrop-filter: saturate(180%) blur(5px);
		background: hsla(0, 0%, 0%, 0.2);
		display: grid;
		grid-template-rows: 12vh auto auto 12vh;
		overflow: hidden;
	}

	@media (min-width: 1024px) {
		.appbar {
			width: 390px;
		}
	}

	.account-zone,
	.menu {
		border-bottom: 1px solid #57565652;
	}

	.account-zone {
		display: flex;
		align-items: center;
		padding: 2rem;
		gap: 1rem;
	}

	.account-zone .avatar {
		display: block;
		width: 4rem;
		height: 4rem;
		border-radius: 50%;
		position: relative;
		overflow: hidden;
		padding: 4px;
		transform: translateZ(0);
		backdrop-filter: saturate(180%) blur(5px);
		background: hsla(0, 0%, 0%, 0.2);
		flex-shrink: 0;
	}

	.account-zone .avatar img {
		width: 100%;
		height: 100%;
		border-radius: 50%;
		top: 0;
		left: 0;
		background-color: rebeccapurple;
	}

	.account-zone span {
		display: block;
		color: #fff;
	}

	.account-zone .name {
		font-size: 1.2rem;
		font-weight: 600;
	}

	.menu {
		padding: 2rem 0rem;
	}

	.menu > span {
		display: block;
		padding: 0rem 2rem;
		margin-bottom: 1rem;
	}

	.menu > ul {
		list-style: none;
		padding: 0rem 2rem;
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(calc(25% - 20px), 1fr));
		gap: 20px;
	}

	.menu > ul > li {
		display: block;
		padding: 0.8rem;
		border-radius: 4px;
		transition: color 0.6s ease, transform 0.6s ease;
		cursor: pointer;
		color: #fff;
	}

	.menu > ul > li:hover {
		color: hsla(0, 0%, 0%, 0.7);
		transform: scale(1.1);
	}

	.menu > ul > li a {
		display: flex;
		align-items: center;
		flex-direction: column;
		gap: 1rem;
		color: inherit;
		text-decoration: none;
	}

	.menu > ul > li img:last-child {
		margin-left: auto;
	}

	.icon {
		width: 2rem;
		height: 2rem;
		background-color: #3b3939;
		border-radius: 4px;
		border: 0;
		outline: none;
	}

	.plus-icon {
		width: 1.5rem;
		height: 1.5rem;
		border-radius: 4px;
		position: relative;
	}

	.plus-icon::before,
	.plus-icon::after {
		content: '';
		position: absolute;
		width: 70%;
		height: 2px;
		background-color: #1d1c1c;
		background-color: #fff;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
	}

	.plus-icon::after {
		transform: translate(-50%, -50%) rotate(90deg);
	}

	/* Notifications */
	.notifications {
		padding: 2rem;
	}

	/* New Actions */
	.new-actions {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		padding: 1rem 2rem;
		gap: 1rem;
	}

	.new-actions > button {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		gap: 0.5rem;
		outline: none;
		border: 0;
		border-radius: 4px;
		transition: background 0.6s ease, transform 0.6s ease;
		background: hsla(0, 0%, 0%, 0.7);
		color: #fff;
	}

	.new-actions > button:hover {
		transform: scale(1.1);
	}

	.new-actions > button span {
		display: block;
		font-size: 0.6rem;
		font-weight: 600;
		text-transform: uppercase;
	}
</style>
