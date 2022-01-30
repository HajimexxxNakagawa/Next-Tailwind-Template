# Nextwind Prototyping Boilerplate

A boilerplate for prototyping with Next.js & Tailwind CSS, which would save your time a lot!

This project is made with...

- Next.js
- TypeScript
- Tailwind CSS
- Storybook
- husky & lint-staged
- scaffdog

## Sammary of Strength

- Tailwind & Storybook are already set!
- Nicely structured folders, which would be familier with OOUI prototyping
- Useful ESlint plugins and rules
  - Tailwind className sort
  - import order
  - unused import deletion
- pre-commit hook is also set!
- Scaffdog generates a nice component folder template!

## Structure

I assume this boilerplate being used in OOUI-aware prototyping. So you would develop like this.

1. Define the type of model (or Object in OOUI) is `@/types` (`@/` means `/src/` here)
2. Create a mock data that follows the model
3. Create UI components under `@/components/model`

And scaffdog will help you a lot. See here!

```zsh
.
├── .husky
├── .scaffdog
├── .storybook
├── public
└── src
    ├── components
    │   ├── model # components related to models
    │   ├── page # components which represents page
    │   └── ui # components indifferent to models
    ├── mocks # mock data related to models
    ├── pages
    │   └── api
    ├── styles
    └── types # type definition of models
```

## Usage

### Development

You can quickly start development with these commands.

```zsh
# package install
yarn

# start localhost
yarn dev

# start storybook
yarn sb
```

### Scaffdog

This document explain the usage of scaffdog in this project.
These command are already set, but you can freely customize. See official document of scaffdog.

**Create a new model**

When you create a new model, use this command at first.

```zsh
npx scaffdog generate model
```

Then, scaffdog will ask you some questions. This is an example of creating Student model.

```zsh
? Please select the output destination directory. . # choose root(.)
? Please enter model name student #enter model name. Multiple words are also fine.

🐶 Generated 2 files!

     ✔ src/types/Student.ts
     ✔ src/mocks/Student.ts

```

**Create a new component related to model**

When you create a new component related to model, use this command at first.

```zsh
npx scaffdog generate model-component
```

Then, scaffdog will ask you some questions. This is an example of creating Student List Component, which is related to Student model.

```zsh
? Please select the output destination directory. . # choose root(.)
? Which model? student # enter model name. Multiple words are also fine.
? Plese enter component name student list # enter component name. Multiple words are also fine.

🐶 Generated 3 files!

     ✔ src/components/model/Student/StudentList/index.ts
     ✔ src/components/model/Student/StudentList/StudentList.tsx
     ✔ src/components/model/Student/StudentList/StudentList.stories.tsx


```

**Create a new page component**

When you create a new page component, use this command at first.

```zsh
npx scaffdog generate page-component
```

Then, scaffdog will ask you some questions. This is an example of creating About page component.

```zsh
? Please select the output destination directory. . # choose root(.)
? Please enter component name about # enter component name. Multiple words are also fine.

🐶 Generated 4 files!

     ✔ src/components/page/About/index.ts
     ✔ src/components/page/About/Page.tsx
     ✔ src/components/page/About/View.tsx
     ✔ src/components/page/About/About.stories.tsx


```

**Create a new ui component**

When you create a new component indifferent to model, use this command at first.

```zsh
npx scaffdog generate ui-component
```

Then, scaffdog will ask you some questions. This is an example of creating Button component.

```zsh

? Please select the output destination directory. . # choose root(.)
? Please enter component name button #enter component name. Multiple words are also fine.

🐶 Generated 2 files!

     ✔ src/components/ui/Button/index.tsx
     ✔ src/components/ui/Button/Button.stories.tsx


```
