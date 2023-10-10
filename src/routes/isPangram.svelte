<script lang="ts">
	let alphabet: string = 'abcdefghijklmnopqrstuvwxyz';
	let userInput: string = '';
	let result: string = '';

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

	function checkSentence() {
		result = isPangram(userInput)
			? 'The sentence is a pangram! ✅'
			: 'The sentence is not a pangram! ❌';
	}
</script>

<h1 class="h1 m-4">Pangram Checker</h1>
<blockquote class="blockquote">
	Pangram is a sentence containing every letter of the alphabet.
</blockquote>
<blockquote class="blockquote">Example: The quick brown fox jumps over the lazy dog.</blockquote>

<div class="fixed inset-0 flex justify-center items-center">
	<div class="bg-blue-500 text-white p-6 rounded">
		<label class="label">
			<span>Enter a sentence:</span>
			<input bind:value={userInput} class="input" type="text" placeholder="Your text here..." />
		</label>
		<button on:click={checkSentence} type="button" class="btn variant-filled mt-4"
			>Check Pangram</button
		>
		<p class="mt-4">{result}</p>
	</div>
</div>
