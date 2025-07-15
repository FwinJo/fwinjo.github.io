<script>
    import Team from "./Team.svelte";
    let { teams, onTeamClick } = $props();
</script>

<div class="teams-list">
    {#each teams as team}
        <Team name={team.name} onClick={() => onTeamClick(team)} />
    {/each}
</div>

<style>
    .teams-list {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 1rem;
        justify-items: center;
        margin: 2rem 0;
    }

    @media (max-width: 900px) {
        .teams-list {
            grid-template-columns: repeat(2, 1fr);
        }
    }

    @media (max-width: 600px) {
        .teams-list {
            grid-template-columns: 1fr;
        }
    }

    :global(.team-card) {
        width: 180px;
        height: 120px;
        display: flex;
        align-items: center;
        justify-content: center;
        box-sizing: border-box;
    }
</style>