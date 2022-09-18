# [Module Bundlers](https://www.youtube.com/watch?v=5IG4UmULyoA)

**What's a module bundler:**

> A module bundler is a tool that takes pieces of JS and their dependencies and bundles them into a signle file. It usually starts with an entry file, and from there it bundles up all of the code needed for that entry file.

#

**There are two main stages of a bundler:**

- Dependency resolution
  - When a new dependency is added to the graph, the user need to perform conflict resolution to determine which version should be added to the graph. Then the metadata should be retrieved so that it's dependencies can be added in turn.
- Packing
  - For the packing it's used pack fucntion, which returns an object/s.

#

# Webpack

**What is webpack:**

> That's a `static module bundler` for modern JS aplications. When webpack processes given application, it internally builds a dependency graph from one or more entry points and then combines every module the current project needs into one or more bundles, which are static assets to serve your content from.

#

- Dependency graph -> Any time one file depends on another, webpack treats this as a dependency. This allows webpack to take non-code assets, such as images or fonts and provide them as dependencies for the user application.

#

**To get started with webpack the user need to understand it's `core concepts`:**

- Entry
  - An entry point indicates which module webpack should use to begin building out it's internal dependency graph.
- Output
  - The output property tells webpack where to emit the bundles it creates and how to name these files.
- Loaders
  - Out of the box, webpack understands only JS and JSON files. Loaders allow webpack to process other types of files and convert them into valid modules that can be consumed by the current application and added to dependency graph.
- Plugins
  - They are a key piece of the webpack ecosystem and provide the community with a powerful way to tap into webpack's compilation process. A plugin is able to hook into key events that are fired throughout each compilation .They can preform a wide range of tasks like bundle optimization, asset managment and injection of environment variables.
- Mode
  - By setting the mode parameter to either `development`, `production` or `none`, you can enable webpack's built-in optimizations that correspond to each environment(The default value is production).
- Browser Compatibility
  - Webpack supports all browsers that are ES5-compliant.
