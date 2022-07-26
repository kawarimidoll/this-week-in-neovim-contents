# This Week In Neovim | Contents

This repository holds the contents of https://this-week-in-neovim.org.

## Organization

News are classified by year, month, and day. The file naming scheme is quite simple `/contents/<year>/<month>/<day>.md`.
For instance:

```
contents/
  |
  + 2021
  |  |
  |  + …
  |
  + 2022/
      |
      + Jul
      |  |
      |  + 15.md
      |  |
      |  + …
```

> An important notice about formatting: both the year and the day are numerals (`2022`, `15`) but the month is not. So
> you have to use `Jul` instead of `06`. This is the case for all the months and the rule is simple: take the name of
> the month, keep only the first three characters and use an uppercase for the first one. `December -> Dec`,
> `August -> Aug`, etc.

At the very beginning of a weekly cycle, a new default Markdown file for the week is created and pushed to a branch `%Y-%M-%d`. PR
are accepted and must target that branch. Notice that the file is dated (year, month, day), and then we _expect_ a
release to be done on that day. If for whatever reason we can’t make it, we will not change the branch name, but we will
update the file _eventually_.

Before the end of the cycle, around Sunday or Monday, a PR is opened to merge `%Y-%M-%d -> master`. Everyone can
partake in that phase of review, but the goal here is to ensure links work, no typo are present, etc., or if anyone want
to withdraw their updates from the weekly updates.

To finish the cycle, the merge commit is created and the article is automatically available on
`https://this-week-in-neovim.org/latest` or `https://this-week-in-neovim.org/<year>/<month>/<day>`.

## How to contribute?

If you want to become a content contributor, you can do different things, but there are some general rules to follow:

1. Always read the current `%Y-%M-%d` branch (and PRs targetting it) to ensure no one has come up with the same
   news as you yet.
2. Open a PR against `%Y-%M-%d` branch by adding new stuff you’ve seen.
3. Ensure your contribution is devoid of bad language and goes straight to the point. See the section about how to
   contribute actual news [here](#how-do-you-write-a-news-pr).
4. Wait for someone to review and merge your contribution.
5. Your news will be added to `master` at the end of the cycle.

If the branch is not created yet, you can even contribute that branch!

1. Create the `%Y-%M-%d` branch. It must start from `master`.
2. Copy the file `news-template.md` in `contents/<year>/<month>/<day>.md`.
3. Open the PR.

## How do you write a news PR?

When opening a PR to add some news to the next weekly, you must always include the following elements:

- The source of the news. It can be a commit on GitHub, a changelog, a blog article, etc. anything, but you must provide
  a link. A chat discussion is not considered “a valid source of information” if we can’t link back to it. The goal is
  to write a list of news, with a link to the actual news so that readers can read further more if they want to.
- A super short description of the change. For instance, _“some-plugin.nvim: add new feature to sort files by size.”_.
- If the news is visual, you are strongly advised to upload some screenshots to GitHub (open an issue, slide the image,
  get the link and simply close your issue tab, do not actually create the issue). **Do not put images in your PRs as
  they will be automatically refused.** If you don’t want to use GitHub, that’s fine, but ensure to use an image
  provider that will remain stable in time.

Each news is a block of both HTML and Markdown. Depending on the category, its header and content might change, so here
is a break-down by category.

### For Core updates

```markdown
- Short description: longer description
```

Nothing really enforced as things should be as much informative and to the point as possible here.

### For community updates: guides, tours, articles, etc.

It should have this form:

```markdown
<h3 id="guide-<plugin-name>">
  <a href="#guide-<plugin-name>">
    Description of the guide
  </a>
</h3>

Description of the guide here. You can start that section with a video or screenshot but don’t forget to upload it
to GitHub via an issue (do not include it in the PR or it will be rejected).

If the guide is not about a plugin, name the anchor and `href` as you please but still use the prefix `guide-`.

- [Reddit](<link to Reddit announcement, if any>)
- [GitHub](<link to GitHub project, if any>)
- [etc.](<any kind of useful link, up to you>)

---
```

### For community updates; new plugins

```markdown
<h3 id="new-<plugin-name>">
  <a href="#new-<plugin-name>">
    <span class="icon-text">
      <span class="icon">
        <i class="fa-solid fa-book"></i>
      </span>
      <span>plugin-name</span>
    </span>
  </a>
</h3>

Description of the new plugin here. You can start that section with a video or screenshot but don’t forget to upload it
to GitHub via an issue (do not include it in the PR or it will be rejected).

- [Reddit](<link to Reddit announcement, if any>)
- [GitHub](<link to GitHub project, if any>)
- [etc.](<any kind of useful link, up to you>)

---
```

The `---` translates to `<hr/>` in HTML and helps a lot delimit plugin section; please do not forget to include it!

The `### pr`

If several news / changes are online for a given project, please do not create several `###` headlines; group everything under the same one.

### For community updates: updates of an existing plugin

Very similar to the previous section, the only thing that changes is the anchor (and `href`):

```markdown
<h3 id="update-<plugin-name>">
  <a href="#update-<plugin-name>">
    <span class="icon-text">
      <span class="icon">
        <i class="fa-solid fa-book"></i>
      </span>
      <span>plugin-name</span>
    </span>
  </a>
</h3>

Description of the new plugin here. You can start that section with a video or screenshot but don’t forget to upload it
to GitHub via an issue (do not include it in the PR or it will be rejected).

- [Reddit](<link to Reddit announcement, if any>)
- [GitHub](<link to GitHub project, if any>)
- [etc.](<any kind of useful link, up to you>)

---
```
