<script lang="ts">
	let alphabet: string = 'abcdefghijklmnopqrstuvwxyz';

	function isPangram(inputString: string): boolean {
		inputString = inputString.toLowerCase();
		let processedString = inputString.replace(/[^a-zA-Z]/g, '');

		for (let element of alphabet.split('')) {
			if (!processedString.includes(element)) {
				return false;
			}
		}

		return true;
	}
</script>
