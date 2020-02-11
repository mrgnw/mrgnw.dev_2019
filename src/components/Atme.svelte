
<script>
	export let text = ""
	$: encoded = encodeURI(text)
	let prefix = "https://twitter.com/intent/tweet?text="
	$: link = `${prefix}${text}`
</script>

<a href="{link}">
	<slot>@ me!</slot>
</a>