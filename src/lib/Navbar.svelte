<script lang="ts">
    import { page } from '$app/stores';
    let currentPath: string;

    $: currentPath = $page.url.pathname;

    const links = [
        {text: "Home", path: "/"},
        {text: "About", path: "/about"},
        {text: "Products", path: "/products"},
        {text: "Shop", path: "/shop"},
        {text: "Contact", path: "/contact"},
    ];
</script>

<ul class="flex w-fit">
    {#each links as {text, path}}
        <li class="px-3 hover:text-red-500 transition-colors">
            <a href={path}>{text}</a>
            {#if currentPath === path}
                <div 
                    class="h-0.5 bg-red-500"
                    style:margin-top="-3px"
                />
            {/if}
        </li>
    {/each}
</ul>