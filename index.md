# Featherweight Project Maintenance

## Maintain 100+ open-source packages

## Jason R. Coombs

Note:

...

## Intro and Background

Note: 22 years in Python, built web-scale enterprise applications on Python

...

## ASP

- Airborne radiation monitoring
- Python 2.0 on IIS 5
- Charting Library
- Utilities

...

## Setuptools

- For publishing re-usable libraries
- Best-in-class

---

# Progression

- Scripts
- MVP, modules on disk
- Source Code Management
- Publish, Share
- Distribute
- Document
- Test
- ...

Note: It's a common story, especially in Python where it's easy to begin coding with minimal infrastructure. You start out with a small project and mature it as you go along.

...

# Adoption

- Adopt a tool
- Encounter bugs
- Improve and add features
- Rely on it
- Maintainer ghost or busy
- Fork or adopt

...

# Repeat

- One little package,
- Two little packages,
- Three little packages,
- [more](https://pypi.org/user/jaraco)...

...

# Consequence

- Overwhelmed
- Burn-out
- Abandon

...

# Solution

Software!

---

# Packaging

- [Python Packaging User's Guide](https://packaging.python.org/)
- irc.freenode.net/#pypa
- Sample project

Note: There are several resources for learning about and developing your packaging solution. But what about automation? How to develop and repeatedly apply these techniques?

...

# Automation

- [cookiecutter](https://pypi.org/project/cookiecutter/)
- [jaraco.develop](https://github.com/jaraco/jaraco.develop/blob/f02c9bd33f0ee9442e2d4b54e6267802fc0f4a2d/jaraco/develop/namespace.py#L52)
- Templates evolve in source code

Note: I started out with some tooling to generate projects from a template. I could iterate on the template and every time I had a new best practice, I could add it to the template and it would be adopted in subsequent projects.

...

## Updates?

- templates only affect new projects

Note: This was great for creating a new project, but I quickly ran up against a problem--how to update the project from last week and three years ago? If only we had a system that could manage the revisions and merge them into the projects.

---

# Source Code Management

- Git, Mercurial, ...

...

# Visual Source Topology

- GUI
  - TortoiseSVN, TortoiseHg
  - SourceTree (git/hg)
- `git log --graph`
- Visualize ancestry

Note: As a quick aside, I want to talk about visualizing your source code history. There are many ways to visualize a source. Years ago on Windows I used the Tortoise suite of tools. When I switched to macOS, I started using SourceTree by Atlassian. If you're not using a tool like this to visualize and create a mental model of your commit histories, you're going to struggle with anything other than a linear history, and will be particularly helpful in understanding the next concepts.

---

# Skeleton

- [Blogged concept](https://blog.jaraco.com/a-project-skeleton-for-python-projects/) (Jan, 2017)
- Store the packaging technique in [one repo](https://github.com/jaraco/skeleton)
- Merge that technique into the source code in another repo
- Inherit and adapt

Note:

...

## Benefits

- Self-documenting
  - Features
  - Conventions
- History of changes
- Flexible adoption strategies
- One change everywhere

Note: Documentation comes along for the ride

...

```shell
$ git log --oneline | wc -l
149
```

...

## Behaviors

- Continuous integration through Travis-CI
- Documentation published through ReadTheDocs
- Releases automated by Twine and CI

Note: Functions and behaviors of the current skeleton include

...

## Inherit and Adapt

- Customize to your details (author name)
- Customize approach (license, CI)
- Improve and contribute upstream
- Ex: YouGov

Note: Upstream here means the (skeleton) repo from which you inherited.

...

## Usage

- New project
- Existing project

---

# Weaknesses

- Merge conflicts
- No templating
- Opinionated
- History is forever

Note: Merge conflicts are common and require fairly intimate understanding of the motivations of both the skeleton and the merged target. There's no templating, so making any customization either must happen repeatedly or be its own derived repo. Because a repo describes essentially one technique, it's inherently opinionated about that technique. Also, the history is forever (next slide).

...

## Git Doesn't Forget

- Unable to roll up past commits
- Brand new project gets all 149 commits

Note: It's both good and bad that the history is there. On one hand, it's nice to see the full ancestry of the changes that became incorporated. On the other hand, it's a lot of clutter and largely uninteresting history distracting from and sometimes burying more essential changes (your code).

...

## Bones

- "Digest" version
- [repo](https://github.com/the-allanc/bones)
- An attempt to periodically collapse changes from skeleton
- Higher stability
- Less noise
- Delayed response
- Disassociated (in code, not in spirit)

---

# Tour

- [portend](https://github.com/jaraco/portend)

Note: Let's take a tour of some real-world example(s).

---

# Q&A

- Twitter/Github: @jaraco
- Slides: http://bit.ly/feather-package
