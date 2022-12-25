<script>
    export let mobileMenuOpen = false;

    const toggleMobileMenu = () => mobileMenuOpen = !mobileMenuOpen;
</script>

<header>
    <!--Header Logo-->
    <img src="./images/logo.svg" alt="Header Logo (Capital Letter W followed by a period.)">

    <!--Desktop Navigation-->
    <nav class="desktop-nav">
        <ul>
            <li>Home</li>
            <li>New</li>
            <li>Popular</li>
            <li>Trending</li>
            <li>Categories</li>
        </ul>
    </nav>
    {#if mobileMenuOpen}
        <button class="nav-buttons" on:click|preventDefault|stopPropagation={toggleMobileMenu}>
            <img src="./images/icon-menu-close.svg" alt="Mobile Menu Close Button Icon">
        </button>
    {:else}
        <button class="nav-buttons" on:click|preventDefault|stopPropagation={toggleMobileMenu}>
            <img src="./images/icon-menu.svg" alt="Mobile Menu Open Button Icon">
        </button>
    {/if}
</header>

{#if mobileMenuOpen}
<nav class="mobile-nav">
    <ul>
        <li>Home</li>
        <li>New</li>
        <li>Popular</li>
        <li>Trending</li>
        <li>Categories</li>
    </ul>
</nav>
{/if}

<style>
    header{
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 3.6rem 1.6rem;
    }

    .nav-buttons{
        background: var(--neutral-off-white);
        border: none;
        z-index: 2;
    }

    .desktop-nav{
        display: none;
    }

    .mobile-nav{
        position: absolute;
        background: rgba(93, 95, 121, 60%);
        top: 0;
        width: 100%;
        height: 100%;
    }

    .mobile-nav ul{
        position: absolute;
        display: flex;
        flex-direction: column;
        gap: 2rem;
        font-size: 24px;
        background: var(--neutral-off-white);
        width: 70%;
        height: 100%;
        left: 30%;
        list-style: none;
        padding: 8rem 2rem;
    }

    @media screen and (min-width: 700px){

        header{
            padding: 3.6rem 0;
        }

        .nav-buttons{
            display: none;
        }

        .mobile-nav{
            display: none;
        }

        .desktop-nav{
            display: block;
        }

        .desktop-nav ul{
            list-style: none;
            display: flex;
            gap: 2rem;
        }
    }
</style>