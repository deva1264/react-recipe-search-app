# 🍴 Forkful - Recipe Search App

Phase 3 · React - Assignment No. 5: **Build a Recipe Search App with React**

A multi-page recipe finder built with **React 18, React Router v6, Axios and Vite**, using the free [TheMealDB](https://www.themealdb.com/api.php) API.

## Run it

```bash
npm install
npm run dev
```

Open the URL Vite prints (usually http://localhost:5173).

## Requirements checklist

| Requirement | Where |
|---|---|
| 4 pages + Navbar with `Link`-based navigation and active highlighting | `src/App.jsx`, `src/components/Navbar.jsx` (`NavLink` adds an `active` class) |
| Custom hook `useRecipes(query)` using Axios returning `{ data, loading, error }` | `src/hooks/useRecipes.js` |
| Controlled search form that calls the hook and shows cards | `src/pages/Recipes.jsx`, `src/components/RecipeCard.jsx` |
| Loading spinner + error message | `src/components/Spinner.jsx`, `ErrorMessage.jsx` |
| Recipe Detail via `useParams` (`/recipes/:id`) | `src/pages/RecipeDetail.jsx` |
| "Save to Favourites" on every card, shown on Favourites page | `RecipeCard.jsx`, `src/pages/Favourites.jsx` |
| Favourites persist across navigation (state lifted to a shared context) | `src/context/FavouritesContext.jsx` |

## Extras beyond the brief

- **Shareable searches** - the submitted query lives in the URL (`/recipes?q=pasta`), so refresh, back button and shared links all work.
- **Surprise me** - picks a random recipe from the API on the home page.
- **Cancelled requests** - Axios calls are aborted with `AbortController` when the query changes or the page unmounts, so stale results never overwrite new ones.
- **A second hook, `useRecipe(id)`** - reuses the same fetching logic for the detail page.
- **Ingredient checklist** - tick off ingredients as you gather them.
- **Favourites survive a page refresh** - state is mirrored to `localStorage`.
- **Navbar badge** shows how many favourites are saved; friendly empty states and a 404 page.

## Structure

```
src/
  components/   Navbar, RecipeCard, Spinner, ErrorMessage
  context/      FavouritesContext (useState lifted into a provider)
  hooks/        useRecipes, useRecipe
  pages/        Home, Recipes, RecipeDetail, Favourites, NotFound
```
