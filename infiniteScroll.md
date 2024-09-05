# Infinite Scroll Blog Posts

This HTML document implements an infinite scroll feature to load blog posts from an API. It fetches posts from the JSONPlaceholder API and displays them on the page as the user scrolls down.

## HTML Structure

The HTML consists of the following main components:

- **Post List**: An unordered list (`<ul>`) with the ID `post-list` where the fetched posts will be displayed.
- **Loading Indicator**: A `<div>` with the ID `loading` that shows a loading message while posts are being fetched.

### HTML Code

```html
<ul id="post-list"></ul>
<div id="loading">Loading...</div>
