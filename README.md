
A front-end framework template for starting projects with a recent version of
either the [Rails API Template]
or the [Express API Template]

## Installation

   account name and repository name.
1. Install dependencies with `npm install`.
1. `git add` and `git commit` your changes.
1. Run the development server with `npm start`.

## Deployment

Before deploying, you first need to make sure the `homepage` key in your
`package.json` is pointing to the correct value. It should be the url of your
deployed application.

To deploy you should first make sure you are on the `master` branch with a
clean working directory, then you can run `npm run deploy` and wait to see if
it runs successfully.


## Structure

The top-level `App` component stores the currently authenticated
user in state, as well as data related to the flash messages. `App` renders the
`Header` component, and a list of routes, each of which render a component from
`src/components`. The `src/api` directory has a component file, `auth.js`, which
contains all the needed `axios` calls pertaining to authentication.

You can follow this pattern in your app as well. For instance, if you are making
an app that keeps track of books, you might want a `src/api/books.js`, which
contains its own `axios` call pertaining to your books resource CRUD actions.
Using a separate directory within `components` for each individual component you
add makes it easy to locate and update components and has the added benefit of
making it easy to create custom styles that apply to that specific component.
To apply component specific styles, add a file to the component's directory such
as `ComponentName.scss` and then import it directly into the component with
`import './ComponentName.scss'`.  This will keep your styles modularized and
make it easier to make changes at the component level.

## Features

### `<AuthenticatedRoute />`

This template contains a handy component for creating routes that require a
user to be authenticated before visiting. This component lives in
`src/auth/components/AuthenticatedRoute.js` and is already required in `App`.
It's a thin wrapper around React Router's `<Route />` component. The only
difference is that it expects a prop called `user`, and if that prop is falsy,
it will render a `<Redirect />` that takes the user to `/`. **To use
it, you must pass it the user as a prop!**

It supports both the `component=` and `render=` attributes, but like `<Route />`
it will not forward props to the component if you use `component=`.

Developers should run these often!

- `npm run nag`: runs code quality analysis tools on your code and complains.
- `npm run make-standard`: reformats all your code in the JavaScript Standard
  Style.
- `npm run start`: generates bundles, watches, and livereloads.
- `npm run build`: place bundled styles and scripts where `index.html` can find
    them
- `npm run deploy`: builds and deploys master branch

## [License](LICENSE)

1. All content is licensed under a CC­BY­NC­SA 4.0 license.
1. All software code is licensed under GNU GPLv3. For commercial use or
    alternative licensing, please contact legal@ga.co.
