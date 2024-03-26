# Teleport
```
The main use case for Teleport is when you need to render a component's content in a different part of the DOM, such as rendering a modal dialog outside the main app root.
```

# why teleport?
```
For positioning reasons
Drag-and-drop interfaces
Scrollable Content: Teleport allows you to render content outside of the scrolling container, ensuring it remains visible even when the container is scrolled.
```

# <slot>
```
slots allow you pass custom template that need to be rendered in a component.

slots helps to maximize reusability of component by replacing the <slot> placeholder in the component with the custom template given when the component is used.
```
# Named Slots
```
Named slots allow you to pass a specific template containing the property v-slot:name to target a specific slot with the property name="name"
```

# MODAL
```
The Modal component lets you create dialogs, popovers, lightboxes, and other elements that force the user to take action before continuing.
```

# Props
```
Props are a way to pass data from the parent component to the child component.

It is a good practice to pass data from parent to child rather than having data present in the child.
"Single source of Truth"
```

# Emits
```
Emits allow child components to emit data for child to parent communication
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
