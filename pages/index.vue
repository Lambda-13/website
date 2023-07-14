<template>
	<div>
		<HeroHeader />

		<main class="content py-12 lg:text-lg lg:py-16 xl:py-24 debris-bg">
            <div class="max-w-screen-xl mx-auto px-4">
                <div class="card mb-8 lg:mb-12">
                    <h2 class="mb-4 lg:mb-5 content-heading content-heading--primary">
                        Ролевая игра с элементами выживания
                    </h2>

                    <p class="mb-4 lg:mb-6">
                        В недалеком будущем члены экипажа космических станций,
                        принадлежащих корпорациям, неустанно работают, чтобы
                        поддерживать работу систем станций. Просто выполнять свою работу
                        недостаточно - им также приходится бороться за выживание в
                        суровой космической среде и справляться с опасностями, которые
                        скрываются во тьме.
                    </p>
                    <p>
                        Расскажите свою собственную историю в мирах Space Station 13,
                        многопользовательской песочнице, которая богата возможностями.
                        Разрабатываемая на протяжении более 20 лет с участием
                        тысячи участников, мир SS13 постоянно меняется.
                    </p>
                </div>

				<TestimonialSlider class="mt-4 mb-6 lg:mt-8 lg:mb-10 lg:mx-10" />

				<div class="flex flex-col lg:flex-row lg:mb-8">
					<div class="flex flex-col mb-8 lg:mr-8 lg:mb-0">
						<h2 class="mb-4 lg:mb-8 content-heading content-heading--primary">
							Геймплейные особенности
						</h2>

						<ul
							class="flex h-full flex-col justify-between gap-4 ml-6 features"
						>
							<li>
								Играйте самые разные роли на станции, начиная от скромных помощников персонала, заканчивая инженерами, поддерживающими питание, и капитаном, правящим всем железной рукой.
							</li>
							<li>
								Взорвите станцию, играя за разных антагонистов: ядерных оперативников цель которых уничтожить станцию, инопланетян которые похищают людей, генокрадов меняющих форму, злых волшебников, и многими другими.
							</li>
							<li>
								Дайте волю своему творчеству и занимайтесь не только ролевой игрой. Множество сложных систем в процессе работы, таких как детальная медицина и исследование загадочных инопланетных артефактов со смертельными, но выгодными наградами делают игровой процесс ещё более интересным
							</li>
							<li>
								Испытайте на себе игровой процесс, управляемый игроками, где нет повторяющихся одинаковых раундов.
							</li>
							<li>
								Откройте для себя древние руины и странных существ на близлежащих планетах и раскройте их историю и секреты.
							</li>
							<li>
								Остерегайтесь всего! Выясните личности предателей среди экипажа с помощью сообразительности или криминалистики.
							</li>
							<li>
								Испытайте случайные профессиональные опасности, такие как разгерметизация отсека, радиационные бури, взломаный Исскуственный Интелект, метеоритные дожди и многое другое.
							</li>
						</ul>
					</div>

					<div
						class="flex gap-6 justify-center flex-wrap lg:justify-start lg:flex-col lg:gap-8 lg:flex-shrink-0 lg:w-4/12"
					>
						<BaseImage
							class="game-shot-card"
							src="/img/about-preview-1.jpg"
							width="1000"
							height="710"
							:img-attrs="{ loading: 'lazy', alt: 'Preview' }"
						/>
						<BaseImage
							class="game-shot-card"
							src="/img/about-preview-2.jpg"
							width="1000"
							height="714"
							:img-attrs="{ loading: 'lazy', alt: 'Preview' }"
						/>
					</div>
				</div>
			</div>
		</main>
	</div>
</template>

<script>
export default {
	name: 'IndexPage',
	layout: 'home',
}
</script>

<style lang="scss" scoped>
.features {
	li {
		position: relative;

		&:before {
			content: '';
			position: absolute;
			top: 10px;
			left: -16px;
			width: 8px;
			height: 8px;
			background: theme('colors.primary');
		}
	}
}
</style>
