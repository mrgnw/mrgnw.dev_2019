
<script>
	export let text = ""
	$: encoded = encodeURI(text)
	let prefix = "https://twitter.com/intent/tweet?text="
	$: link = `${prefix}${text}`
	// todo: automatically add location?
</script>

<a href="{link}">
	<slot>@ me!</slot>
</a>