<template>
	<div class="slider text-center h-32 sm:h-24 md:h-20">
		<transition-group
			tag="div"
			class="h-full relative overflow-hidden"
			:name="transitionName"
		>
			<div
				v-if="show"
				:key="current"
				class="slide absolute inset-0 flex flex-col justify-center"
			>
				<div class="slide-inner">
					<p class="font-serif sm:text-lg lg:text-xl">
						&#8220;{{ slides[current].quote }}&#8221;
					</p>
					<p class="font-semibold uppercase tracking-wider opacity-75">
						{{ slides[current].author }}
					</p>
				</div>
			</div>
		</transition-group>
	</div>
</template>

<script>
// Adapted with love from https://codepen.io/adaban/pen/qoqLJb

export default {
	data: () => ({
		current: 0,
		direction: 1,
		transitionName: 'fade',
		show: false,
		loop: 0,
		slides: [
			{
				quote:
					'Space Station 13 — один из лучших симуляторов песочницы, доступных как бесплатно, так и по иной причине.',
				author: 'Rock, Paper, Shotgun',
			},
			{
				quote:
					'Почти все возможно, каждый раунд отличается, и все игроки безумны. И это лишь некоторые из причин, по которым я люблю Космическую станцию 13.',
				author: 'PC GAMER',
			},
			{
				quote:
					"Космическая станция 13 стала жертвой культистов... Что я могу сделать? Я могу взять швабру и начать оттирать лужу крови. Потому что это моя работа. Потому что я обычный уборщик.",
				author: 'PCGamesN',
			},
			{
				quote:
					'Необходимость коммуникации между незнакомцами из Интернета создает развлекательное состояние полнейшего хаоса. Ожидайте взрыв. Много взрывов.',
				author: 'PC GAMER UK',
			},
			{
				quote:
					'Научно-фантастическая многопользовательская песочница с таким же дерьмовым дизайном, что и Dwarf Fortress.',
				author: 'Rock, Paper, Shotgun',
			},
			{
				quote:
					'Space Station 13 отличается от любой другой игры, потому что, как и многие другие замечательные вещи, она появилась случайно.',
				author: 'https://return.life - Robert Mariani',
			},
		],
	}),

	mounted() {
		this.show = true
		this.loop = setInterval(() => {
			this.slide(1)
		}, 10000)
	},

	beforeDestroy() {
		clearInterval(this.loop)
	},

	methods: {
		slide(dir) {
			this.direction = dir
			dir === 1
				? (this.transitionName = 'slide-next')
				: (this.transitionName = 'slide-prev')
			const len = this.slides.length
			this.current = (this.current + (dir % len) + len) % len
		},
	},
}
</script>

<style lang="scss" scoped>
/* FADE IN */
.fade-enter-active {
	transition: opacity 1s;
}
.fade-enter {
	opacity: 0;
}

/* GO TO NEXT SLIDE */
.slide-next-enter-active,
.slide-next-leave-active {
	transition: transform 0.5s ease-in-out;
}
.slide-next-enter {
	transform: translate(100%);
}
.slide-next-leave-to {
	transform: translate(-100%);
}

/* GO TO PREVIOUS SLIDE */
.slide-prev-enter-active,
.slide-prev-leave-active {
	transition: transform 0.5s ease-in-out;
}
.slide-prev-enter {
	transform: translate(-100%);
}
.slide-prev-leave-to {
	transform: translate(100%);
}
</style>
