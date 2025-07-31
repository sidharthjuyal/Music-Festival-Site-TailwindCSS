# Music-Festival-Site-TailwindCSS
This is a Music Festival Site made using TailwindCSS. ( Practice for Responsiveness )

# Layers
- Base layer
  - body, h2, button (Applies style to an html tag, general base styles)
- Components layer
  - .btn, .third-partt-lib (Recommended not to create components, they are not out of the box)
- Utilities layer
  - .text-2xl, .bg-white (They are out of the box tailwind classes)

Note: Utilities override components and components override base layer.

# layer vs. theme
```html
@theme {
    --font-sans-serif: sans-serif, serif;
    --font-quicksand: "Quicksand", serif;
}

@layer base {
    body {
        font-family: var(--font-quicksand);
    }
}
```

# creating a component
```html
@layer components {
    .menu-item {
        @apply relative flex h-full items-center p-4 cursor-pointer font-bold text-pink-200 hover:text-zinc-200 hover:bg-white/10 transition-colors ease-in-out;
    }
}
using components like this increases bundle size, recommended to us eutilities classes and component should be used in a limited way.
```

# creating a custom variant
```html
@custom-variant group-open {
    &:is(:where(.group):is(.open, [open], :popover-open, :open) *) {
       @slot;
    }
}
```
