<script>
    import NavBar from "./NavBar.svelte";
    import Teams from "./Teams.svelte";

    let page = $state("home");
    let selectedTeam = $state(null);

    let teams = [
        { name: "Herren 1" },
        { name: "Herren 2" },
        { name: "Herren 3" },
        { name: "Damen 1" },
        { name: "Damen 2" },
        { name: "Damen 3" },
        { name: "U18 Männlich" },
        { name: "U18 Weiblich" },
        { name: "U16 Männlich" },
        { name: "U16 Weiblich" },
        { name: "U14 Männlich" },
        { name: "U14 Weiblich" },
        { name: "U12 Mixed" }
    ];

    function increment() {
        count += 1;
    };

    function handleNavigate(navTo) {
        page = navTo;
    };

        function handleTeamClick(team) {
        selectedTeam = team;
        page = "team";
    };

</script>

<div class="page-wrapper">
    <h1 class="title">FTG Frankfurt Basketball</h1>
    <NavBar navigate={handleNavigate} />

    <main>
        {#if page === 'home'}
            <h1>Hello World!</h1>
        {:else if page === 'teams'}
            <h1>Teams</h1>
            <Teams teams={teams} onTeamClick={handleTeamClick} />
        {:else if page === 'about'}
            <h1>About</h1>
            <p>This is the about page.</p>
        {:else if page === 'contact'}
            <h1>Contact</h1>
            <p>This is the contact page.</p>
        {:else if page === 'team' && selectedTeam}
            <h1>Team: {selectedTeam.name}</h1>
            <p>Details about {selectedTeam.name} go here.</p>
            <button onclick={() => page = 'teams'}>Back to Teams</button>
        {:else if page === 'privacy'}
            <h1>Data Privacy Policy</h1>
            <p>Your privacy policy content goes here.</p>
        {:else if page === 'impressum'}
            <h1>Impressum</h1>
            <p>Your impressum content goes here.</p>
        {/if}        
    </main>

    <footer>
        <button onclick={() => page = 'privacy'}>Data Privacy Policy</button>
        <button onclick={() => page = 'impressum'}>Impressum</button>
    </footer>
</div>

<style>
    :global(body) {
        min-height: 100vh;
        margin: 0;
        display: flex;
        flex-direction: column;
    }
    .page-wrapper {
        min-height: 100vh;
        display: flex;
        flex-direction: column;
    }
    .title {
        text-align: center;
        margin: 1rem 0;
        font-size: 3rem;
        color: #333;
    }
    main {
        flex: 1;
        text-align: center;
        padding: 2rem;
        font-family: sans-serif;
    }
    button {
        margin-top: 1rem;
        padding: 0.5rem 1rem;
        font-size: 1rem;
        cursor: pointer;
    }
    p {
        margin-top: 0.5rem;
        font-size: 1.1rem;
    }
    footer {
        display: flex;
        justify-content: center;
        gap: 2rem;
        padding: 2rem 0 1rem 0;
        background: #f8f8f8;
        border-top: 1px solid #ddd;
    }
    footer button {
        background: #333;
        color: #fff;
        border: none;
        padding: 0.5rem 1rem;
        border-radius: 4px;
        cursor: pointer;
    }
    footer button:hover {
        background: #555;
    }    
</style>