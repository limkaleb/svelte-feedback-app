<script>
    import Card from "./Card.svelte";
    import Button from "./Button.svelte";
</script>


<Card>
    <header>
        <h2>How would you rate service with us?</h2>
    </header>

    <form>
        <!-- Rating Select -->
        <div class="input-group">
            <input type="text" placeholder="Tell us something that keeps you coming back">
            <button>Send</button>
        </div>
    </form>
</Card>

