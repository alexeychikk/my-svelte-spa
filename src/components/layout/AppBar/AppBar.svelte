<script lang="ts">
  import { createEventDispatcher } from 'svelte';
  import IconEmailOutline from 'svelte-material-icons/EmailOutline.svelte';
  import IconGithub from 'svelte-material-icons/Github.svelte';
  import IconLinkedIn from 'svelte-material-icons/Linkedin.svelte';
  import IconMenu from 'svelte-material-icons/Menu.svelte';
  import { Link } from 'svelte-routing';

  import IconFolderSrcOpen from '../../../assets/icons/folder-src-open.svg?component';
  import IconButton from '../../common/IconButton';
  import Breadcrumbs from '../Breadcrumbs';
  import Navigation from '../Navigation';

  import styles from './AppBar.module.scss';

  const dispatch = createEventDispatcher();
</script>

<header class={styles.appBar}>
  <nav class={styles.toolbar}>
    <div class={styles.headingWrapper}>
      <IconButton
        class={styles.folderButton}
        aria-label="GitHub"
        on:click={() => dispatch('openSkillsDrawer')}
      >
        <IconFolderSrcOpen />
      </IconButton>

      <h6 class={styles.myName}>
        <Link to="/">Alex Zinkevych</Link>
      </h6>
      <a
        class={styles.linkButton}
        href="https://github.com/alexeychikk"
        target="_blank"
        rel="external nofollow"
      >
        <IconButton aria-label="GitHub" tabindex="-1">
          <IconGithub />
        </IconButton>
      </a>
      <a
        class={styles.linkButton}
        href="https://www.linkedin.com/in/alex-zinkevych/"
        target="_blank"
        rel="external nofollow"
      >
        <IconButton aria-label="LinkedIn" tabindex="-1">
          <IconLinkedIn />
        </IconButton>
      </a>
      <a
        class={styles.linkButton}
        href="mailto:alexdarkmm@gmail.com"
        target="_blank"
      >
        <IconButton aria-label="E-Mail" tabindex="-1">
          <IconEmailOutline />
        </IconButton>
      </a>
      <IconButton
        class={styles.menuButton}
        aria-label="open navigation drawer"
        on:click={() => dispatch('openNavigationDrawer')}
      >
        <IconMenu />
      </IconButton>
    </div>

    <Navigation class={styles.navigation} />
  </nav>

  <Breadcrumbs class={styles.mobileBreadcrumbs} />
</header>
