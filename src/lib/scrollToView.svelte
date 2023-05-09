<script lang="ts">
	export function scrollIntoView(id:string) {
		const element = document.getElementById(id);
		if (element) {
			element.scrollIntoView({ behavior: 'smooth' });
		}
	}
</script>
