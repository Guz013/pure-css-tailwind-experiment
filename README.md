# Tailwind in pure CSS

This is a small learning and coding experiment of trying to recreate a similar
feel and utility approach of Tailwind utility classes using just pure CSS.
Without any build step, pre- or post-processor.

---

## Why and how

The idea is to utilize a combination of
[CSS custom properties (variables)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
and [inline styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_is_structured#inline_styles).

```html
<!-- Tailwind's utility classes -->
<section class="p-2">
    <h1 class="p-5 hover:p-2 px-1">
        Hello, world
    </h1>
    <h2 class="text-red md:p-5 sm:hover:p-5">
        This is a test
    </h2>
</section>

<!-- Experiment's "utility variables" -->
<section style="--p:var(--2);">
    <h1 style="--p:var(--5);--hover-p:var(--2);--px:var(--1);">
        Hello, world
    </h1>
    <h2 style="--text:var(--red);--md-p:var(--5);--sm-hover-p:var(--5)">
        This is a test
    </h2>
</section>
```

Yes, writing inline styles and the custom properties syntax is more cumbersome than
using utility classes. However, the idea is to compromise some characters and looks,
for removing a third party dependency and reeling more on the web standards.

Also, understand how to apply things such as, what I'm calling, "utility variables"
can be useful for people creating component libraries. Since it could add a bit of
liberty and customization, things like padding and margin could be easily customized,
and not hard-coded by the library. There will be always exceptions for designs systems,
so having a way to customize without a build step, configuration file, or additional
dependency, could be useful.

---

## Progress

All implementation code is available in the [`style.css`](./style.css) file, which
contains comments explaining decisions and compromises. Just remember that it is a
draft and will have bugs and not a production-level quality, again, this is just
a experiment.

Currently implemented utilities/features/ideas are:
- How box properties could be handled (padding, margin, etc.);
- Responsive values (values based on screen size);
- State values (`hover:`, `focus:`, etc.);
- Flex and Grid layout utilities;
- Text colors;
- Spacing scales;

---

© 2024 Gustavo "Guz" L. de Mello
Unless otherwise noticed, this repository is licensed under the public domain, as
determined by the [WTFPL license](./LICENSE).
