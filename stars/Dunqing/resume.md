---
project: resume
stars: 364
description: Writing Resume with Markdown, Supports deploy to Vercel, Netlify, Cloudflare. 使用 Markdown 编写简历，支持部署到 Vercel、Netlify 和 Cloudflare。
url: https://github.com/Dunqing/resume
---

WYSIWYG Online resume | Stackblitz Playground | 中文

Introduction
------------

### Purpose

To allow resumes to be previewed anytime, anywhere, written in the Markdown syntax that programmers are most familiar with, and free of charge!

Supported Features
------------------

-   Dark mode support
-   HTML embedding support
-   PDF printing support
-   Online preview support
-   Custom template support
-   Multiple template combination support
-   Style override support
-   More personalized templates

Usage
-----

### create-resumejs

Quickly create a resume project, supports deployment on Vercel

1.  Create

pnpm create resumejs

1.  Choose a template
    
2.  Write your README.md
    
3.  Finish your resume!
    

@resumejs/components
--------------------

Import as components into your own project

### Download

pnpm add @resumejs/components

### 使用

import { Resume } from '@resumejs/components'

export default function App() {
  const resume \= \`
    # Name
    ## Personal Information
    ## Work Information
  \`
  return <Resume\>{resume}</Resume\>
}

### Usage Example

-   vite-ant-design-pro

@resumejs/resume
----------------

-   CLI support, usage is the same as Vite
-   By default, use the README.md in the running directory as your resume markdown
-   Supports the vite.config.ts configuration file

> You can directly use create-resumejs to create a project

### Install

pnpm add @resumejs/resume

Dependencies react and react-dom need to be installed.

pnpm add react react-dom

### Development

resume dev

### Build

resume build

### Preview

resume preview

### Custom Templates

resume dev --template @resumejs/template-nova
resume build --template @resumejs/template-nova

Reference example

Templates
---------

-   @resumejs/template-default Default template
-   @resumejs/template-nova

**Default resume template**

How to customize the template?
------------------------------

### Customize the markdown syntax for writing resumes

1.  The content under the first-level title includes the information of the resume header with the first-level title as the header. You can customize the `header` component.

-   The first-level title is the name. You can customize the `header-name` component.
-   The picture is used as the avatar. You can customize the `header-avatar` component.
-   Wrap all list items. You can customize the `header-content` component.
-   Each list is a row. You can customize the `header-row` component.
-   The item in the list is a column. You can customize the `header-col` component.

1.  The first paragraph below the third-level title

-   The table will be changed to the description information of the third-level title, and you can customize the `card`, `card-item`, `card-item-label`, `card-item-value` components.
-   The first line of text below the title or Table will be changed to the description content, and you can customize the `description` component.

1.  FrontMatter (dark mode, Github, print button)

-   You can customize the toolbox component.

### Example

-   Default template

Deploy
------

This is very simple, just click the button above to deploy to Vercel. You can also deploy to other platforms that support Vite.

Others
------

This project is tested with BrowserStack.

MIT LICENSE
