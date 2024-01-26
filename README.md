<<<<<<< HEAD
# tabi

A fast, lightweight, and modern [Zola](https://www.getzola.org) theme with multi-language support. It aims to be a personal page and home to blog posts.

See a live preview (and the theme's documentation) [here](https://welpo.github.io/tabi).

Explore the [Sites Using tabi section](#sites-using-tabi) to see real-world applications.

> tabi (旅): Journey.

![tabi](https://github.com/welpo/tabi/raw/main/light_dark_screenshot.png)

tabi has a perfect score on Google's Lighthouse audit:

![lighthouse](https://raw.githubusercontent.com/welpo/tabi/main/lighthouse_score.png)

## Features

- [X] [Set any language as default](https://welpo.github.io/tabi/blog/faq-languages/#how-do-i-set-a-default-language-for-my-site). Set your base site to Chinese, Spanish, French, Hindi… or any [other supported language](/i18n). The theme's interface will be translated accordingly.
- [X] [Integration with remote repositories](https://welpo.github.io/tabi/mastering-tabi-settings/#git-repository-integration) on GitHub, GitLab, Gitea & Codeberg for commit history and showing the site source.
- [X] Dark and light themes. Defaults to the OS setting, with a switcher in the navigation bar.
- [X] Thorough documentation. See [Mastering tabi Settings: A Comprehensive Guide](https://welpo.github.io/tabi/blog/mastering-tabi-settings/).
- [X] Perfect Lighthouse score (Performance, Accessibility, Best Practices and SEO).
- [X] [Comprehensive multi-language support](https://welpo.github.io/tabi/blog/faq-languages/#how-does-tabi-handle-multilingual-support). Add as many languages as you wish.
- [X] Support for [comments using giscus, utterances, Hyvor Talk, or Isso](https://welpo.github.io/tabi/blog/comments/).
- [X] Code syntax highlighting with colours based on [Catppuccin](https://github.com/catppuccin/catppuccin) Frappé.
- [X] [Local search](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#search) with an accessible, multi-lingual interface.
- [X] [KaTeX](https://katex.org/) support for mathematical notation.
- [X] [Stylized and human readable Atom feed](https://welpo.github.io/tabi/atom.xml).
- [X] [Stylized and human readable sitemap](https://welpo.github.io/tabi/sitemap.xml).
- [X] [Mail encoding](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#encoded-email) for spam protection.
- [X] All JavaScript can be [fully disabled](https://welpo.github.io/tabi/blog/javascript/).
- [X] [Customizable Table of Contents](https://welpo.github.io/tabi/blog/toc/).
- [X] [Customizable secure headers](https://welpo.github.io/tabi/blog/security/).
- [X] [Copy button for code blocks](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#copy-button-on-code-blocks).
- [X] [Quick navigation buttons](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#quick-navigation-buttons).
- [X] [Custom copyright notice](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#copyright).
- [X] [Custom canonical URLs](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#canonical-url).
- [X] [Custom shortcodes](https://welpo.github.io/tabi/blog/shortcodes/).
- [X] [Customizable skins](https://welpo.github.io/tabi/blog/customise-tabi/).
- [X] [Footnote backlinks](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#footnote-backlinks).
- [X] [Social media cards](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#social-media-cards).
- [X] Responsive design.
- [X] [Projects page](https://welpo.github.io/tabi/projects/).
- [X] [Archive page](https://welpo.github.io/tabi/archive/).
- [X] [Social links](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#social-media-icons).
- [X] [Tags](https://welpo.github.io/tabi/blog/mastering-tabi-settings/#tags).

## Quick start

Once you have installed Zola 0.17.0 or newer:

```bash
git clone https://github.com/welpo/tabi.git
cd tabi
zola serve
```

Open http://127.0.0.1:1111 in the browser.

## Installation

To add tabi to you existing Zola site:

0. Initialize a Git repository in your project directory (if you haven't already):

```
git init
```

1. Add the theme as a git submodule:

```
git submodule add https://github.com/welpo/tabi.git themes/tabi
```

Or clone the theme into your themes directory:

```
git clone https://github.com/welpo/tabi.git themes/tabi
```

### Required configuration

2. Enable the theme in your `config.toml`:

```
theme = "tabi"
```

3. Set a `title` in your `config.toml`:

```
title = "Your Site Title"
```

4. Configure code block highlighting in your `config.toml`:

```toml
[markdown]
highlight_code = true
highlight_theme = "css"
```

5. Create a `content/_index.md` file with the following content:

```
+++
title = "Home"
paginate_by = 5 # Set the number of posts per page
template = "index.html"
+++
```

If you want to serve your blog posts from a different path, such as `blog/`, add a `section_path` in the `[extra]` section of `content/_index.md` (this file will need pagination):

```
[extra]
section_path = "blog/_index.md"
```

6. If you want an introduction section (see screenshot above), add these lines to `content/_index.md`:

```
[extra]
header = {title = "Hello! I'm tabi~", img = "img/main.webp", img_alt = "Your Name" }
```

The content outside the front matter will be rendered between the header title and the posts listing. In the screenshot above, it's the text that reads "tabi is a fast, lightweight, and modern Zola theme…".

7. If you want a multilingual site, you will need to set up each language. In `config.toml`, set the title and taxonomies for each language, like:

```toml
[languages.es]
title = "~/tabi"
taxonomies = [{name = "tags", feed = true}]
```

You will need an `_index.{language_code}.md` per language for each section (e.g. /blog or /projects) that you want to enable in that language.

The same is true for individual posts, which should have the exact same name as the default language, with an extra `.{code}` before the extension (e.g. the Spanish version of `security.md` would be `security.es.md`).

This configuration allows the language switcher to take the user to the translation of the current URL. If a translation doesn't exist, the 404 page will be displayed, with an explanation in each language set in the config.

To learn more about multilingual support, see the [Frequently Asked Questions](https://welpo.github.io/tabi/blog/faq-languages/).

## Sites Using tabi

| Website | Creator | Description  | Site Source   |
| - | - | - | - |
| [osc.garden](https://osc.garden) | Óscar Fernández ([welpo](https://github.com/welpo)) | Data science, psychology, and Zola | [Source](https://github.com/welpo/osc.garden) |
| [sandip.live](https://sandip.live) | Sandip G ([sandman](https://github.com/sandman)) | Startups, tech and the good life | [Source](https://github.com/sandman/sandman.github.io) |
| [seadve.github.io](https://seadve.github.io/) | Dave Patrick Caberto ([SeaDve](https://github.com/SeaDve/)) | Personal blog and portfolio with custom CSS | [Source](https://github.com/SeaDve/seadve.github.io) |
| [donovan.is](https://donovan.is) | [Donovan Glover](https://github.com/donovanglover) | Linux, Rust, and Full Stack Web Development | [Source](https://github.com/donovanglover/donovan.is) |
| [mikufan.page](https://mikufan.page) | [Nadia](https://github.com/nyadiia) | Personal blog | [Source](https://github.com/nyadiia/mikufan.page) |
| [tim-boettcher.online](https://tim-boettcher.online/) | [Tim Böttcher](https://codeberg.org/Tim-Boettcher/) | Insights and ramblings of a deafblind programmer | [Source](https://codeberg.org/Tim-Boettcher/tim-boettcher-online/) |
| [andwati.github.io](https://andwati.github.io) | [Ian Andwati](https://github.com/andwati) | Echos from within | [Source](https://github.com/andwati/andwati.github.io) |

Using tabi? Feel free to create a PR and add your site to this list.

## Inspiration

This theme was inspired by:
- [shadharon](https://github.com/syedzayyan/shadharon) — tabi started as a fork of [syedzayyan](https://github.com/syedzayyan)'s theme;
- [tailwind-nextjs-starter-blog](https://github.com/timlrx/tailwind-nextjs-starter-blog);
- [abridge](https://github.com/Jieiku/abridge);
- [internetVin's blog](https://internetvin.ghost.io).

## Contributing

Please do! We appreciate bug reports, improvements to translations or documentation (however minor), feature requests…

Take a look at the [Contributing Guidelines](/CONTRIBUTING.md) to learn more.

## License

The code is available under the [MIT license](./LICENSE).
||||||| merged common ancestors
=======
# mystaticwebsite



## Getting started

To make it easy for you to get started with GitLab, here's a list of recommended next steps.

Already a pro? Just edit this README.md and make it your own. Want to make it easy? [Use the template at the bottom](#editing-this-readme)!

## Add your files

- [ ] [Create](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#create-a-file) or [upload](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#upload-a-file) files
- [ ] [Add files using the command line](https://docs.gitlab.com/ee/gitlab-basics/add-file.html#add-a-file-using-the-command-line) or push an existing Git repository with the following command:

```
cd existing_repo
git remote add origin https://gitlab.com/BobZhangzz/mystaticwebsite.git
git branch -M main
git push -uf origin main
```

## Integrate with your tools

- [ ] [Set up project integrations](https://gitlab.com/BobZhangzz/mystaticwebsite/-/settings/integrations)

## Collaborate with your team

- [ ] [Invite team members and collaborators](https://docs.gitlab.com/ee/user/project/members/)
- [ ] [Create a new merge request](https://docs.gitlab.com/ee/user/project/merge_requests/creating_merge_requests.html)
- [ ] [Automatically close issues from merge requests](https://docs.gitlab.com/ee/user/project/issues/managing_issues.html#closing-issues-automatically)
- [ ] [Enable merge request approvals](https://docs.gitlab.com/ee/user/project/merge_requests/approvals/)
- [ ] [Set auto-merge](https://docs.gitlab.com/ee/user/project/merge_requests/merge_when_pipeline_succeeds.html)

## Test and Deploy

Use the built-in continuous integration in GitLab.

- [ ] [Get started with GitLab CI/CD](https://docs.gitlab.com/ee/ci/quick_start/index.html)
- [ ] [Analyze your code for known vulnerabilities with Static Application Security Testing (SAST)](https://docs.gitlab.com/ee/user/application_security/sast/)
- [ ] [Deploy to Kubernetes, Amazon EC2, or Amazon ECS using Auto Deploy](https://docs.gitlab.com/ee/topics/autodevops/requirements.html)
- [ ] [Use pull-based deployments for improved Kubernetes management](https://docs.gitlab.com/ee/user/clusters/agent/)
- [ ] [Set up protected environments](https://docs.gitlab.com/ee/ci/environments/protected_environments.html)

***

# Editing this README

When you're ready to make this README your own, just edit this file and use the handy template below (or feel free to structure it however you want - this is just a starting point!). Thanks to [makeareadme.com](https://www.makeareadme.com/) for this template.

## Suggestions for a good README

Every project is different, so consider which of these sections apply to yours. The sections used in the template are suggestions for most open source projects. Also keep in mind that while a README can be too long and detailed, too long is better than too short. If you think your README is too long, consider utilizing another form of documentation rather than cutting out information.

## Name
Choose a self-explaining name for your project.

## Description
Let people know what your project can do specifically. Provide context and add a link to any reference visitors might be unfamiliar with. A list of Features or a Background subsection can also be added here. If there are alternatives to your project, this is a good place to list differentiating factors.

## Badges
On some READMEs, you may see small images that convey metadata, such as whether or not all the tests are passing for the project. You can use Shields to add some to your README. Many services also have instructions for adding a badge.

## Visuals
Depending on what you are making, it can be a good idea to include screenshots or even a video (you'll frequently see GIFs rather than actual videos). Tools like ttygif can help, but check out Asciinema for a more sophisticated method.

## Installation
Within a particular ecosystem, there may be a common way of installing things, such as using Yarn, NuGet, or Homebrew. However, consider the possibility that whoever is reading your README is a novice and would like more guidance. Listing specific steps helps remove ambiguity and gets people to using your project as quickly as possible. If it only runs in a specific context like a particular programming language version or operating system or has dependencies that have to be installed manually, also add a Requirements subsection.

## Usage
Use examples liberally, and show the expected output if you can. It's helpful to have inline the smallest example of usage that you can demonstrate, while providing links to more sophisticated examples if they are too long to reasonably include in the README.

## Support
Tell people where they can go to for help. It can be any combination of an issue tracker, a chat room, an email address, etc.

## Roadmap
If you have ideas for releases in the future, it is a good idea to list them in the README.

## Contributing
State if you are open to contributions and what your requirements are for accepting them.

For people who want to make changes to your project, it's helpful to have some documentation on how to get started. Perhaps there is a script that they should run or some environment variables that they need to set. Make these steps explicit. These instructions could also be useful to your future self.

You can also document commands to lint the code or run tests. These steps help to ensure high code quality and reduce the likelihood that the changes inadvertently break something. Having instructions for running tests is especially helpful if it requires external setup, such as starting a Selenium server for testing in a browser.

## Authors and acknowledgment
Show your appreciation to those who have contributed to the project.

## License
For open source projects, say how it is licensed.

## Project status
If you have run out of energy or time for your project, put a note at the top of the README saying that development has slowed down or stopped completely. Someone may choose to fork your project or volunteer to step in as a maintainer or owner, allowing your project to keep going. You can also make an explicit request for maintainers.
>>>>>>> be40f7c997c8d405922d24891575915caedb262f
