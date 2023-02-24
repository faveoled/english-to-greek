<script>
	let input = 'Put your English text here';
	let output = '';
	
	function GREEKIFY(english) {
		let alphabet = {
			"a": "α",
			"b": "β",
			"c": "γ",
			"d": "δ",
			"e": "ε",
			"f": "φ",
			"g": "τζ",
			"h": "η",
			"i": "ι",
			"j": "τζει",
			"k": "κ",
			"l": "λ",
			"m": "μ",
			"n": "ν",
			"o": "ο",
			"p": "π",
			"q": "κιου",
			"r": "ρ",
			"s": "σ",
			"t": "τ",
			"u": "θ",
			"v": "βε",
			"w": "ω",
			"x": "χ",
			"y": "υ",
			"z": "ζ"
		}
		let convertString = '';
		for(let i = 0; i < english.length; ++i) {
			let ch = alphabet[english[i]];
			if (ch) {
				if (english[i].toUpperCase() == english[i]) {
					convertString += ch.toUpperCase()
				} else {
					convertString += ch
				}
			} else {
				convertString += english[i]
			}
		}
		return convertString;
	}

	function handleClick() {
		output = GREEKIFY(input)
	}
</script>

<h1>Convert English (Latin) to Greek symbols</h1>

<textarea bind:value={input} id="input" name="input" rows="8" cols="50"></textarea>
<br>
<button on:click={handleClick}>
	Convert to greek symbols
</button>
<br>
<textarea bind:value={output} id="output" name="output" rows="8" cols="50"></textarea>
