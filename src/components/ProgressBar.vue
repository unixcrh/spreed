<!--
  - @copyright Copyright (c) 2020 Marco Ambrosini <marcoambrosini@pm.me>
  -
  - @author Marco Ambrosini <marcoambrosini@pm.me>
  -
  - @license GNU AGPL version 3 or any later version
  -
  - This program is free software: you can redistribute it and/or modify
  - it under the terms of the GNU Affero General Public License as
  - published by the Free Software Foundation, either version 3 of the
  - License, or (at your option) any later version.
  -
  - This program is distributed in the hope that it will be useful,
  - but WITHOUT ANY WARRANTY; without even the implied warranty of
  - MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
  - GNU Affero General Public License for more details.
  -
  - You should have received a copy of the GNU Affero General Public License
  - along with this program. If not, see <http://www.gnu.org/licenses/>.
-->

<docs>
</docs>

<template>
	<div class="progress-bar">
		<div class="progress-bar__loaded" :style="progressLoadedWidth" />
		<div class="progress-bar__total" />
	</div>
</template>

<script>
export default {
	name: 'ProgressBar',

	props: {
		/**
		 * An integer between 1 and 100
		 */
		value: {
			type: Number,
			required: true,
		},
	},

	computed: {

		progressLoadedWidth() {
			return {
				width: `${this.value}px`,
			}
		},
	},

}
</script>

<style lang="scss" scoped>

.progress-bar {
	position: relative;
	width: 100%;
	&__loaded,
	&__total {
		position: absolute;
		top: 0;
		left: 0;
		height: 4px;
	}
	&__loaded {
		background-color: var(--color-primary-element-light);
		z-index: 1;
	}
	&__total {
		width: 100%;
		background-color: var(--color-box-shadow);;
	}
}

</style>
