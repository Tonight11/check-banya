<script setup></script>

<template>
	<span>
		<svg
			width="30"
			height="30"
			viewBox="0 0 30 30"
			fill="none"
			xmlns="http://www.w3.org/2000/svg"
		>
			<circle
				cx="14.6944"
				cy="14.6606"
				r="13.6701"
				transform="rotate(90 14.6944 14.6606)"
				stroke-width="1.82269"
			/>
			<path
				d="M15.1719 13.0668V20.5471H13.3638V13.0668H15.1719ZM15.4198 10.8869C15.4198 11.0425 15.3882 11.1883 15.325 11.3244C15.2618 11.4605 15.1768 11.5795 15.0698 11.6816C14.9678 11.7837 14.8463 11.8663 14.7053 11.9295C14.5644 11.9878 14.4137 12.017 14.2533 12.017C14.0977 12.017 13.9495 11.9878 13.8085 11.9295C13.6725 11.8663 13.5534 11.7837 13.4513 11.6816C13.3492 11.5795 13.2666 11.4605 13.2034 11.3244C13.1451 11.1883 13.1159 11.0425 13.1159 10.8869C13.1159 10.7265 13.1451 10.5758 13.2034 10.4349C13.2666 10.2939 13.3492 10.1724 13.4513 10.0704C13.5534 9.96828 13.6725 9.88809 13.8085 9.82976C13.9495 9.76657 14.0977 9.73498 14.2533 9.73498C14.4137 9.73498 14.5644 9.76657 14.7053 9.82976C14.8463 9.88809 14.9678 9.96828 15.0698 10.0704C15.1768 10.1724 15.2618 10.2939 15.325 10.4349C15.3882 10.5758 15.4198 10.7265 15.4198 10.8869Z"
			/>
		</svg>
	</span>
</template>

<style lang="scss" scoped>
	span {
		width: 3.2rem;
		height: 3.2rem;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		background-color: $default-color;
		box-shadow: 1px 4px 12px rgba(166, 175, 205, 0.36);
	}
	.setting-aside__info-item {
		& path {
			fill: $green-color;
		}
	}

	.cabinet-card-ads__badje {
		& svg {
			width: 1.2rem;
			height: 1.2rem;
		}
	}

	.cabinet-card-favorite__badje {
		& svg {
			width: 2rem;
			height: 2rem;
		}
	}
</style>
