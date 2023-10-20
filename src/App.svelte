<script>
	let doc = ''
	import { marked } from 'marked'
</script>

<main>
	<textarea bind:value={doc}/>
	<h3>Preview</h3>
	<iframe title="main" srcdoc={marked.parse(doc)}></iframe>

	<button on:click={() => { 
		navigator.clipboard.writeText(marked.parse(doc)) 
	}}>Copy Html</button>
</main>

<style>
	textarea {
		color: black;
		width: 100%;
		height: 150px;
		padding: 12px 20px;
		box-sizing: border-box;
		border: 2px solid #ccc;
		border-radius: 4px;
		background-color: #f8f8f8;
		font-size: 16px;
		resize: none;
		font-size: 18px;
	}

	h3 {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	button {
		background-color: rgb(200, 200, 215);
		border: 1.5px solid rgb(38, 33, 33);
		border-radius: 10px;
		color: black;

		transition: border-radius 0.35s;
	}

	button:hover {
		border-radius: 14px;
	}

	iframe {
		width: 100%;
		height: 150px;
		padding: 12px 20px;
		box-sizing: border-box;
		color: black;
	}
</style>
