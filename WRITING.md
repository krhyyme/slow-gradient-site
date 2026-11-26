# Writing posts

```sh
hugo new posts/my-post/index.md   # new draft (page bundle: images live beside it)
hugo server -D                     # preview at http://localhost:1313, drafts included
```

Set `draft: false` and merge to `main` to publish.

## Tufte features

```markdown
{{< newthought >}}Opening words{{< /newthought >}} start a section in small caps.

A claim.{{< sidenote >}}Numbered note in the margin.{{< /sidenote >}}
A claim.{{< marginnote >}}Unnumbered note in the margin.{{< /marginnote >}}
```

Sidenotes and margin notes must sit **inside a sentence**, not on a line of
their own. On their own line they render outside a paragraph and end up
off-screen.

## Math

Rendered to HTML at build time by KaTeX (`layouts/_markup/render-passthrough.html`).

```markdown
Inline: $\nabla_\theta \mathcal{L}(\theta)$ or \(x^2\)

Display:
$$
\theta_{t+1} = \theta_t - \eta \nabla_\theta \mathcal{L}(\theta_t)
$$
```

A LaTeX error fails the build and names the post, so typos can't ship.

## Figures

Put the image next to the post's `index.md`, then:

```markdown
{{< figure src="loss-curve.png" caption="Training loss." >}}
{{< figure src="loss-curve.png" type="margin" caption="In the margin." >}}
{{< figure src="loss-curve.png" type="full" caption="Full width." >}}
```

## Code

Fenced blocks with a language get syntax highlighting:

````markdown
```python
loss.backward()
```
````
