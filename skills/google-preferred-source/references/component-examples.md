# Component examples

Generic examples. Adapt names, styles and file locations to the project; reuse
its existing button or link primitive and design tokens instead of the
placeholder classes here.

## The URL, defined once

```ts
// Next to the site's existing canonical URL constant.
export const SITE_URL = "https://example.com";

export const GOOGLE_PREFERRED_SOURCE_URL =
  "https://www.google.com/preferences/source?q=" +
  encodeURIComponent(new URL(SITE_URL).host);
```

## Plain HTML

```html
<a
  class="btn btn-secondary preferred-source"
  href="https://www.google.com/preferences/source?q=example.com"
  target="_blank"
  rel="noopener"
>
  <svg aria-hidden="true" focusable="false" width="20" height="20"><!-- icon --></svg>
  <span>Prefer us on Google</span>
  <span class="visually-hidden">(opens in a new tab)</span>
</a>
```

```css
.preferred-source {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  min-height: 44px;
  max-width: 100%;
  padding: 0.5rem 1rem;
  /* Colors come from the site's tokens so light and dark both work. */
  color: var(--color-text);
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-md);
}
.preferred-source:focus-visible {
  outline: 2px solid var(--color-focus);
  outline-offset: 2px;
}
```

## Next.js / React (server component)

```tsx
// components/preferred-source-button.tsx
import { GOOGLE_PREFERRED_SOURCE_URL } from "@/lib/site";

type Props = { variant?: "default" | "compact"; className?: string };

export function PreferredSourceButton({ variant = "default", className }: Props) {
  return (
    <a
      href={GOOGLE_PREFERRED_SOURCE_URL}
      target="_blank"
      rel="noopener"
      className={[
        "inline-flex min-h-11 max-w-full items-center gap-2 rounded-md border",
        "border-border bg-card px-4 py-2 text-sm text-foreground",
        "hover:bg-accent focus-visible:outline-2 focus-visible:outline-offset-2",
        className,
      ].filter(Boolean).join(" ")}
    >
      <GoogleIcon aria-hidden="true" className="size-5 shrink-0" />
      <span className="flex flex-col">
        <span className="font-medium">Prefer us on Google</span>
        {variant === "default" && (
          <span className="text-muted-foreground">
            See more of our stories in Google Search.
          </span>
        )}
      </span>
      <span className="sr-only">(opens in a new tab)</span>
    </a>
  );
}
```

No `"use client"`: the component has no state or effects, so it renders on the
server. `GoogleIcon` stands for whatever icon component the site already uses.

Placement:

```tsx
// End of an article
<PreferredSourceButton />

// Footer
<PreferredSourceButton variant="compact" />
```

## Test (Testing Library + Vitest or Jest)

```tsx
import { render, screen } from "@testing-library/react";
import { PreferredSourceButton } from "@/components/preferred-source-button";

it("links to Google's source preferences for the site host", () => {
  render(<PreferredSourceButton />);
  const link = screen.getByRole("link", {
    name: /prefer us on google.*\(opens in a new tab\)/i,
  });
  expect(link).toHaveAttribute(
    "href",
    "https://www.google.com/preferences/source?q=example.com",
  );
  expect(link).toHaveAttribute("target", "_blank");
  expect(link.getAttribute("rel")).toContain("noopener");
});
```

Assert the literal expected URL rather than importing the constant, so the test
catches a wrong host.
