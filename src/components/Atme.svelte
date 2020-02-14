
<script>
	export let text = ""
	let prefix = "https://twitter.com/intent/tweet?text="
	$: link = `${prefix}${encodeURI(text)}`
</script>

<a href="{link}" target="_blank">
	<slot>@ me!</slot>
</a>