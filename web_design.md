## One page
Design a single page website
https://github.com/nqthqn/one-page

## Writing an e-book
Very helpful guide to how a person wrote an ebook
https://pascalprecht.github.io/posts/writing-an-ebook#announcing-the-pre-sale-launch

### Website
One page

Used this script to generate ebook reader files. Basically just markdown files compiled to a book using pandoc!
```sh
rm -rf output/*

pandoc \
  --pdf-engine=xelatex \
  -o output/rebase.pdf \
  source/chapters/foreword.md \
  source/chapters/introduction.md \
  source/chapters/a-quick-look-behind-the-scenes.md \
  source/chapters/anatomy-of-a-git-commit.md \
  source/chapters/a-branch-is-just-a-pointer.md \
  source/chapters/merge-strategies.md \
  source/chapters/a-quick-detour-on-reset.md \
  source/chapters/rebasing.md \
  source/chapters/interactive-rebasing.md \
  source/chapters/cherry-picking.md \
  source/chapters/appendix-a.md \
  source/chapters/appendix-b.md \
  source/chapters/appendix-c.md \
  source/chapters/thank-you.md \
  --toc

pandoc \
  -o output/rebase.epub \
  source/meta \
  source/chapters/foreword.md \
  source/chapters/introduction.md \
  source/chapters/a-quick-look-behind-the-scenes.md \
  source/chapters/anatomy-of-a-git-commit.md \
  source/chapters/a-branch-is-just-a-pointer.md \
  source/chapters/merge-strategies.md \
  source/chapters/a-quick-detour-on-reset.md \
  source/chapters/rebasing.md \
  source/chapters/interactive-rebasing.md \
  source/chapters/cherry-picking.md \
  source/chapters/appendix-a.md \
  source/chapters/appendix-b.md \
  source/chapters/appendix-c.md \
  source/chapters/thank-you.md \
  --toc

kindlegen output/rebase.epub -o rebase.mobi
```

### Other things

Got advice & advertised on IndieHacker, Hacker News

Started selling the book before writing the book!

Book cover in Google drawings!

He said it - Start less, and do more

Great github blog & UI https://pascalprecht.github.io/

### ([link](https://www.indiehackers.com/interview/how-i-grew-my-business-to-six-figures-with-seo-c7719a77c7!)) Building a website revenue stream

- Google Tag Manager - Click tracking on website
- SquareSpace -  WYSIWYG website
- Webflow - **No code** wed builder
- Advertisement engine using Bubble
- SEO - Search engine optimization, is very important to get high quality, monetizable users