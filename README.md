# Commands
- `hugo server -D` : Run the Hugo development server with draft content enabled (remove `-D` to exclude drafts).
- `hugo` : Build the static site for production.
    - After building, the output will be in the `public/` directory and pushing to main will automatically trigger github actions to build and deploy the site.
- `hugo new posts/post-name.md` : Create a new post using the default archetype.
