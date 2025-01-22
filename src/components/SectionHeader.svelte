<script>
let { title, children } = $props();
</script>

<h4 class="fw-normal mt-4">{title}</h4>

<div class="text-muted">{@render children?.()}</div>
