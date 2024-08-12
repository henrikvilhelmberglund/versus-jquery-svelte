# Versus-jquery-Svelte

This is a Svelte5+SvelteKit implementation of [versus-js](https://github.com/jbanes/versus-js). The goal was to end up with a more realistic project that was more readable.

LOC: longer (mostly because of readability)
File size: smaller, even though this project includes a router etc

## Important files

`+layout.svelte` - wraps the whole app and puts the Pager components and main content on every page.
`/lib/Pager.svelte` - Pager component which renders the navbar.
`/1` up to 5 - real routes with HTML content.

## Improvements

- Title and meta desc tags were added.
- Pager div tag changed to nav.
- Pager has real links instead of just clickable spans.  
- Pager sets `aria-current` on current page.
- Red color changed to FireBrick (WCAG).
- Pager uses `aria-current` for the color.
- Main content div tag changed to main.
- Real routes instead of just displaying a number.
- CSS changed to have one property per line instead of all properties on a single line.
- Unused .page:active CSS rule was removed.

Original create-svelte readme below

---

# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/main/packages/create-svelte).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm create svelte@latest

# create a new project in my-app
npm create svelte@latest my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.
