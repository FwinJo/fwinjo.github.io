<script>
    let { name, onClick } = $props();
</script>

<button type="button" class="team-card" onclick={onClick}>
    <h2>{name}</h2>
</button>

<style>
    .team-card {
        background: #f0f0f0;
        border-radius: 8px;
        padding: 1rem;
        margin: 1rem;
        cursor: pointer;
        box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        transition: box-shadow 0.2s;
    }
    .team-card:hover {
        box-shadow: 0 4px 16px rgba(0,0,0,0.2);
        background: #e90f0f;
    }
</style>