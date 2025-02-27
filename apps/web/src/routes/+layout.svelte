<script>
    import { autoModeWatcher, AppShell, AppBar } from '@skeletonlabs/skeleton';
    import { Avatar } from '@skeletonlabs/skeleton';
    import "../app.css";
  
    if (typeof window !== 'undefined') {
        autoModeWatcher();
    }
</script>

<svelte:head>
    {@html '<script>(' + autoModeWatcher.toString() + ')();</script>'}
</svelte:head>
  
<AppShell>
    <!-- AppBar Slot -->
    <svelte:fragment slot="header">
        <AppBar>
            <svelte:fragment slot="lead">
                <h1 class="text-xl uppercase">cuddlepuff</h1>
            </svelte:fragment>
            <svelte:fragment slot="trail">
                <button class="btn variant-filled-primary">Sign In</button>
                <Avatar src="https://i.pravatar.cc/" />
            </svelte:fragment>
        </AppBar>
    </svelte:fragment>
    <!-- Sidebar Slot -->
    <svelte:fragment slot="sidebarLeft">
        <aside class="bg-surface-500/5 w-56 p-4">
            <nav class="list-nav">
                <ul>
                    <li><a href="/">Home</a></li>
                    <li><a href="/about">About</a></li>
                </ul>
            </nav>
        </aside>
    </svelte:fragment>
  
    <!-- Main Content -->
    <slot />
</AppShell>