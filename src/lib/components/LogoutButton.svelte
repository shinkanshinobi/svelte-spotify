<script lang="ts">
	import { invalidateAll } from '$app/navigation';
</script>


<form
		method="POST"
		action="/api/auth/logout"
		on:submit|preventDefault={async () => {
			const resp = await fetch('/api/auth/logout', {
				method: 'POST',
				headers: {
					accept: 'application/json'
				}
			});
			if (resp.ok) {
				invalidateAll();
			}
		}}
	>
		<button type="submit">Logout</button>
	</form>