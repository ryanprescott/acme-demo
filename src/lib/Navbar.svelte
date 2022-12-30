<script lang="ts">
    import { page } from '$app/stores';
    let path: string;

    $: path = $page.url.pathname;

    const links = [
        {text: "Home", link: "/"},
        {text: "About", link: "/about"},
        {text: "Products", link: "/products"},
        {text: "Shop", link: "/shop"},
        {text: "Contact", link: "/contact"},
    ];
</script>

<ul class="flex w-fit">
    {#each links as link}
        <li class="px-3 hover:text-red-500 transition-colors">
            <a href={link.link}>{link.text}</a>
            {#if path === link.link}
                <div 
                    class="h-0.5 bg-red-500"
                    style:margin-top="-3px"
                />
            {/if}
        </li>
    {/each}
</ul>