<script setup>
	import img1 from '~/assets/img/promotions/1.jpg';
	import img2 from '~/assets/img/promotions/2.jpg';
	import img3 from '~/assets/img/promotions/3.jpg';
	import { useWindowSize } from '@vueuse/core';
	const isLarge = ref(true);

	const { width } = useWindowSize();
	watchEffect(() => {
		if (width.value <= 768) {
			isLarge.value = false;
		} else {
			isLarge.value = true;
		}
	});
	onMounted(() => {
		if (width.value <= 768) {
			isLarge.value = false;
		}
	});

	const relatedProduct = ref([
		{
			type: 'Сауны',
			name: 'Сауна Дионис-СПА',
			img: img1,
			metro: 'Павелецкая',
			walk: '13 мин пешком',
			price: '22 300',
		},
		{
			type: 'Сауны',
			name: 'Сауна Дионис-СПА',
			img: img2,
			metro: 'Павелецкая',
			walk: '13 мин пешком',
			price: '22 300',
		},
		{
			type: 'Сауны',
			name: 'Гостевые домики Сан-Поль',
			img: img3,
			metro: 'Павелецкая',
			walk: '13 мин пешком',
			price: '22 300',
		},
		{
			type: 'Сауны',
			name: 'Мини-отель Беседка',
			img: img1,
			metro: 'Павелецкая',
			walk: '13 мин пешком',
			price: '22 300',
		},
		{
			type: 'Сауны',
			name: 'Баня-сауна отеля Катюша',
			img: img2,
			metro: 'Павелецкая',
			walk: '13 мин пешком',
			price: '22 300',
		},
	]);

	const nav = ref([
		{
			text: 'Бани и сауны',
			active: false,
		},
		{
			text: 'Номера',
			active: true,
		},
		{
			text: 'Услуги',
			active: false,
		},
		{
			text: 'Предбанник',
			active: false,
		},
	]);

	const activeLink = item => {
		if (item.active === true) {
			return;
		}
		nav.value.forEach(i => (i.active = false));
		item.active = true;
	};
</script>

<template>
	<div class="card card-related">
		<div class="card-related__content">
			<div class="card-related__top">
				<div class="card-related__title h1">Похожи сауны</div>
				<ul v-if="isLarge" class="nav card-related__nav">
					<li v-for="item in nav" :key="item.text" class="nav__item">
						<button
							class="nav__link card-related__link h4"
							:class="{ active: item.active }"
							@click="activeLink(item)"
						>
							{{ item.text }}
						</button>
					</li>
				</ul>
				<UISwiperButton v-if="isLarge" />
			</div>
			<div class="card-related__row">
				<ProductCardRelatedRequest
					v-for="item in relatedProduct"
					:img="item.img"
					:metro="item.metro"
					:type="item.type"
					:name="item.name"
					:walk="item.walk"
					:price="item.price"
				/>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
	.card-related {
		margin-top: 2rem;
		padding: 4rem 0;
		&__content {
		}

		&__top {
			display: flex;
			align-items: center;
			justify-content: space-between;
			margin-bottom: 4rem;
			padding: 0 2.9rem;
		}

		&__title {
		}

		&__nav {
		}

		&__link {
			background-color: transparent;
			cursor: pointer;
			&.active {
				font-size: 1.6rem;
				color: $green-color;
				position: relative;

				&::before {
					content: '';
					position: absolute;
					height: 0.6rem;
					width: 125%;
					background-color: $green-color;
					left: -0.7rem;
					border-radius: 0px 2px 2px 0px;
					bottom: -1.5rem;
				}
			}
		}

		&__row {
			display: flex;
			@media screen and (max-width: 768px) {
				flex-wrap: wrap;
			}
		}
	}

	.nav {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 5.6rem;
		&__item {
		}
		&__link {
		}
	}
</style>
