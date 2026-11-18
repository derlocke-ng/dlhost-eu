# dlhost-eu

The pages of dlhost.eu, the website of a [Kiwi Network](https://github.com/derlocke-ng/kiwi-server).
It is a template: start the website of your own network from a copy (*Use this template* on
GitHub).

## How it works

The network's control node serves the site at its name and `www.`. It takes the pages from this
repository at one pinned commit and adds what only the network knows: the services that are open
to the Internet and whether they work, the sign-up page, the status page.

In the fleet file, on the machine with the `control` module:

```yaml
control:
  website_hostname: dlhost.eu
  website_repo: https://github.com/derlocke-ng/dlhost-eu
  website_commit: <the commit to show, 40 hexadecimal digits>
```

Then point the name and `www.` at the master in DNS and apply the master and that machine. A
change to the site is a commit here, a new `website_commit` and an apply.

## What is in it

| Path | What it is |
|---|---|
| `site.yaml` | the site's name, tagline, colour, and its pages in the menu's order (the first is the front page) |
| `pages/NAME.md` | one page each; its first `# ` line is its title |
| `assets/` | images and other files, at `/assets/NAME` |

## The Markdown

A small part of Markdown: `#`, `##` and `###` headings, paragraphs, `-` and `1.` lists, `>`
quotes, `---` rules, code blocks between three backticks, and links, `**strong**`, `*emphasis*`
and `` `code` `` in a line. A link to `terms` opens the page `terms`. HTML in a page is shown as
text: nothing in this repository can put script on the site.

## Releases

`VERSION` holds the version. Pin a release's commit in the fleet file, not a branch.
