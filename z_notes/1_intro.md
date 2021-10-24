create graphql api for a prepopulated blog

https://app.graphcms.com

https://app.graphcms.com/ff30a9e80bf749d495d42c5006703ec6/master

api endpoint

https://app.graphcms.com/ff30a9e80bf749d495d42c5006703ec6/master/settings/api-access#root

==

https://app.graphcms.com/ff30a9e80bf749d495d42c5006703ec6/master/graphiql

query Posts {
posts {
title
slug
date
excerpt
tags
coverImage{
url
}
}
}

==

svelte@next to create sveltekit project

npm init svelte@next blog_spence

==

- install tailwind and tailwind config

npx svelte-add@latest tailwindcss

===

env-cmd - .env
daisyui - Tailwind CSS Components

npm i -D graphql-request graphql env-cmd daisyui @tailwindcss/typography

==

npm run dev -- --open --port 3333
