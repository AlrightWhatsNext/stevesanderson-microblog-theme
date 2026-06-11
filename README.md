# Micro.blog theme — Steve Sanderson (spike + build)

This is a custom [Micro.blog](https://micro.blog) theme (Hugo-based) for `stevesanderson.com`.

## What this currently is: a Phase 0 **de-risk spike**

Before porting the full marketing page, this minimal theme tests the three things that could break on
Micro.blog's hosted Hugo:

1. **Posts render server-side** — the homepage ranges over your titled posts. If you have titled posts
   but see a big "NO POSTS RENDERED" warning, the known newer-Hugo bug is present on the selected Hugo
   version (step back to an older version in Design → Hugo Version).
2. **Cal.com loads from the footer** — a floating "Schedule a conversation" button should appear
   bottom-right (scripts are allowed in templates/footer, stripped in post bodies).
3. **Custom CSS applies** — the page should be off-white with a slate-bordered note box and serif
   headings.

## Steve's setup steps (Micro.blog account)

1. **Create a free test blog:** Micro.blog → Posts → Design → Edit Custom Themes (a free second blog
   like `username-test.micro.blog`). Don't touch the live blog yet.
2. **Seed posts:** publish 2–3 **titled** test posts on the test blog.
3. **Connect this theme:** Design → Edit Custom Themes → New Theme → pick **Blank**, then clone this
   repo's public Git URL. Assign the theme to the **test blog**.
4. **Pin Hugo version:** Design → Hugo Version. Try the current default first. If posts don't render,
   step back to an older selectable version.
5. **Verify** the three checks above on the published test-blog URL (the *server* build, not local).

## Layout structure

```
layouts/
  _default/baseof.html     base wrapper (head, main block, footer partial)
  _default/list.html       /blog archive + post lists
  _default/single.html     individual post page
  index.html               homepage (spike: posts test + CSS test)
  partials/head.html       CSS + meta
  partials/custom_footer.html   Cal.com embed (the script test)
static/custom.css          minimal styles (CSS test)
theme.toml                 theme metadata
config.json                default params
```

Once the three checks pass, the full marketing page (hero, Who, What-I-bring, How-I-help, How-I-work,
Proof, Insights, Engage) is ported into `index.html` from
`milestones/define-and-choose-positioning/website-mockup.html`.
