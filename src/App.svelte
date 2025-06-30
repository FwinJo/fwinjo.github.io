<script>
    let name = "world";
    let count = 0;

    function increment() {
        count += 1;
    }
</script>

<main>
    <h1>Hello {name}!</h1>
    <input bind:value={name} placeholder="Enter your name" />
    <br />
    <button on:click={increment}>Count up</button>
    <p>Number of toggles: {count}</p>
</main>

<style>
    main {
        text-align: center;
        padding: 2rem;
        font-family: sans-serif;
    }
    input {
        margin-top: 1rem;
        padding: 0.5rem;
        font-size: 1rem;
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
</style>