---
title: "What's the Headless Component"
seoTitle: "What's the Headless Component"
seoDescription: "Know why you should use it, or not"
datePublished: Sat May 20 2023 09:46:17 GMT+0000 (Coordinated Universal Time)
cuid: clhvt1ix3001z09l55jojfwq2
slug: whats-the-headless-component
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/ylveRpZ8L1s/upload/a59669b71694bca05fce0da589d62042.jpeg
tags: components, headless

---

You've heard more or less of the Headless Component, but before you use it, you must know what's the Headless Component and when to use it.

# What's the Headless Component

For component, it consists of UI(Elements and Styles) and Logic. Unlike traditional components, such as Bootstrap, Headless Components just provides Logic or just provide Elements and Logic. What they have in common is that they provide UnStyle components.

For just provides Logic, you can try [React Aria](https://react-spectrum.adobe.com/react-aria/index.html), it's provides a set of React Hooks. It looks like this:

```typescript
import { useRef } from "react"
import { useToggleButton } from "react-aria"
import { useToggleState } from "react-stately"

import type { PropsWithChildren } from "react"

type ToggleButtonProps = PropsWithChildren

function ToggleButton(props: ToggleButtonProps) {
  const ref = useRef(null)
  const state = useToggleState(props)
  const { buttonProps, isPressed } = useToggleButton(props, state, ref)

  return (
    <button
      {...buttonProps}
      className={`${
        isPressed
          ? (state.isSelected ? "bg-green-900"  : "bg-gray-300") // eslint-disable-line prettier/prettier
          : (state.isSelected ? "bg-green-700" : "bg-gray-200") // eslint-disable-line prettier/prettier
      } px-2 text-base`}
    >
      {props.children}
    </button>
  )
}

export default ToggleButton
```

For just provides Elements and Logic, you can try [Headless UI](https://headlessui.com/), and it looks this:

```typescript
import { useState } from 'react'
import { Switch } from '@headlessui/react'

function MyToggle() {
  const [enabled, setEnabled] = useState(false)

  return (
    <Switch
      checked={enabled}
      onChange={setEnabled}
      className={`${
        enabled ? 'bg-blue-600' : 'bg-gray-200'
      } relative inline-flex h-6 w-11 items-center rounded-full`}
    >
      <span className="sr-only">Enable notifications</span>
      <span
        className={`${
          enabled ? 'translate-x-6' : 'translate-x-1'
        } inline-block h-4 w-4 transform rounded-full bg-white transition`}
      />
    </Switch>
  )
}
```

Which style you prefer, is your choice.

# Why you shouldn't use Headless Components

People will tell you many reasons why you should use Headless Components, but I will say you just one reason to use Headless Components: you need to custom components deeply.

Have you ever thought that why we need Headless Components? Imagine that, when you need to custom an internal component library. How would you do? Create from zero to one? Or create based on open-source component libraries? I think most people would choose the latter.

We all know that the UI and Logic of traditional components are coupled, so it's very hard to custom them deeply. If you can finish your jobs based on open-source component libraries, why do you need to add styles to Headless Components to get the job done?