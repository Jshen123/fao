<template>
	<div id="home" class="view">
		<div class="view-container">
			<div id="title-banner" class="stripe align-center">
				<div class="stripe-content">
					<h1 class="title">Fake Artist Online</h1>
				</div>
			</div>
			<div class="stripe flex-center">
				<home-menu></home-menu>
			</div>
			<div class="stripe">
				<div id="about-content" class="stripe-content normal-text align-center">
					<p>
						A Fake Artist Goes to New York is created by <strong>Oink Games</strong>
					</p>
                    <p>
                        If you enjoy the game, please support the creator here:
                        <a href="https://oinkgms.com/en/a-fake-artist-goes-to-new-york"
							>A Fake Artist Goes to New York</a
						>.
                    </p>
					<p>
						Enjoy the online version? Send a tip to the developer:
						<a href="https://ko-fi.com/krackocloud">Ko-fi</a>
					</p>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
import HomeMenu from './home-menu';
export default {
	name: 'HomeView',
	components: {
		HomeMenu,
	},
};
</script>
