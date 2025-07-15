<script >
    let { navigate } = $props();

</script>

<nav>
    <ul>
        <li><button onclick={() => navigate('home')}>Home</button></li>
        <li><button onclick={() => navigate('teams')}>Teams</button></li>
        <li><button onclick={() => navigate('about')}>About</button></li>
        <li><button onclick={() => navigate('contact')}>Contact</button></li>
    </ul>
</nav>

<style>
    nav {
        background: rgba(233,25,31,1);
        color: #fff;
        padding: 1rem;
    }
    ul {
        list-style: none;
        display: flex;
        gap: 2rem;
        margin: 0;
        padding: 0;
    }
    li button {
        background: none;
        border: none;
        color: #fff;
        font-weight: bold;
        cursor: pointer;
        font-size: 1rem;
    }
    li button:hover {
        text-decoration: underline;
    }
</style>