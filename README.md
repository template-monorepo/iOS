# Template Monorepo: iOS

A strongly-opinionated monorepo boilerplate template for setting up an iOS workspace that comes with
a boilerplate plugin generator for incorporating different tools like deployment.

The boilerplate generator sources plugins from any git repo that can install a new service
(like a new web server), set up your DevOps on AWS even for newly generated services, or
privately create a new service that can be shared with your team only.

### Other templates

- [Template Monorepo: Frontend](https://github.com/template-monorepo/frontend)
- [Template Monorepo: Infra](https://github.com/template-monorepo/infra)
- [Template Monorepo: Backend](https://github.com/template-monorepo/backend)
- [Template Monorepo: Android](https://github.com/template-monorepo/android)
- [Template Monorepo: Desktop](https://github.com/template-monorepo/desktop)

[Plugins](https://github.com/template-monorepo/plugins) are available for this template.

## Introduction

I have a lot of opinions on what's worked and what I wished my organizations or the ones I've joined
started off with. I also have a startup philosophy that platforming, combining loosely related
products in one industry into one business from the start, enterprise SaaS, government and defense
SaaS, and physical products as of November 2023 (but as far back as November 2021 when I started
diving into startups) is the future of the startup industry.

With that startup philosophy and as a software engineer understanding software lives in everything,
I've created a monorepo template that is strongly opinionated for what organizations who fit in the
aforementioned startup belief face:

- Scaling

That is pretty much it. Scaling. Code/resource-wise and team wise.

But that doesn't mean create microservices from the start (should you ever have microservices? ;).
In fact, you should only have one server until you need to add another via autoscaling.

Why does all this boilerplate matter? I litter this throughout [docs/opinion.md](./docs/opinions.md),
but a lot of things listed are best practices if you expect long-term success. There is a separate
doc called [docs/adoption.md](./docs/adoption.md) that lists what tools to consider adopting as you
scale. Those are two separate documents for how I think about going into new projects technically.
But never ever over-complicate stuff. This is boilerplate code such that you'll never need to think
in a complicated manner.

**Yes**: tests are necessary. You never know when you'll refactor code due to business reasons.
Don't debate that lol.

## Getting Started

In this repository, press the green button "Use this template". Clone the default branch only.
Then, clone the repository.

### Usage

You can start the backend by running `python tasks.py`

## My Opinions

Visit [docs/opinions.md](./docs/opinions.md) for how I came to decide what tools to include in this
boilerplate code.

Visit [docs/adoption.md](./docs/adoption.md) for which services, in my opinion, to adopt as you
scale.

## License

This repository is licensed under the Apache 2.0 license which can be found in the
[LICENSE](./LICENSE) file.
