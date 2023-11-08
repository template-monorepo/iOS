# My Opinions

## Management Philosophies

- **SwiftUI**: it's come a long way, but with, iOS 17, by the time you deploy your app, many users
  you might be targeting is around this version or above. SwiftUI is the future of iOS development,
  so it's best to adopt it early and use UIKit when needed.

## Setup Philosophies

- ### File architecture
  - **Monorepo**: If you don't plan on multiple iOS apps, then ignore this. A monorepo is great
    for applications that share very common patterns. A notable company that separates by repository
    is Microsoft for all their apps including Outlook and Teams.
  - **Separate frontend from backend**: for organizational purposes, the [template-monorepo](https://github.com/template-monorepo)
    organization decided to split frontends from each other and the backend for organizational
    purposes. There is tooling for generating Swift code from the backend OpenAPI file during
    development that will be included in the networking portion.
  - **TCA**: [The Composable Architecture](https://github.com/pointfreeco/swift-composable-architecture) is a library for building applications in a
    consistent and understandable way. It takes some of the best practices the industry has learned.
    For an Android equivalent (that template-monorepo uses, see [square/workflow-kotlin](https://github.com/square/workflow-kotlin)).
    To see why I believe in this split, see [Confused? Oxymorons](#confused-oxymorons).
    - Highly recommend this read: [On composable, modular frontends](https://increment.com/frontend/on-composable-modular-frontends/)
- ### Tooling
  - **Bazel**: helps set up iOS projects. It is a build tool for many languages.
  - **Python**: Python as a scripting language is versatile and commonly utilized in
    `template-monorepo` templates.
  - **Direnv**: Direnv is a great tool for managing environment variables. It's a great tool for
    managing secrets and keeping them out of your repository. It's also a great tool for managing
    environment variables for different services.
  - **Click**: `click` is an easy-to-use CLI tool for Python. It's a great tool for managing
    commands for your repository.
  - **Fastlane**: a great tool for managing iOS builds and deployments.
  - **Formatters and checkers**:
    - **pre-commit**: pre-commit is a great tool for linting, formatting, and more. It's a great tool
      for enforcing code quality and standards before committing.
    - **SwiftLint**: a tool that lints your Swift code
- ### Components
  - **Backend integration**: following modularization and composability, there is a code generation
    tool that'll set up all the data structures for serialization/deserialization of JSON using
    OpenAPI docs.
  - **HTTP networking**: a networking layer has been created for you that is modularized and
    composable. It is also set up to work with the backend integration tool.
- ### Testing
  - **GitHub Actions**: a CI/CD pipeline is set up for you with zero integrations with other GitHub
    apps to test and deploy your apps.

## Confused? Oxymorons

- Square Workflow Kotlin vs. TCA: it's good practice to maintain the same architecture and thus the
  same terminology, thinking, state diagrams, etc. But the TCA and Workflow, albeit different and
  developed by different people, share extremely similar concepts but provide the best of their
  respective platforms. The Swift version of Square workflow is not as intuitive. What both
  frameworks share include unidirectional data flow, composability, and dependency injection.
  Sharing frameworks in Square's case means greater interactions for planning and each team can
  review each other's business logic meaning overall increase in team interaction.
  - A notable example of a company that have a similar split in architectural decision is the
    Browser Company that develops the Arc browser. So long as concepts are similar, it's great.
  - The reason TCA is better than Square's workflow for iOS are enumerable, but the primary reason
    is intuition and optimization for developer experience.
- Why not use React Native: there are benefits to programming with React Native, but even a somewhat
  complex app such as adding purchases can make the development time of React Native the same as
  building two apps unless you're completely new to app development. The benefits of React Native
  are that you can share code between iOS and Android; in native practice, people also have shared
  C++ code between iOS and Android, but it adds development overhead such that tooling needs to be
  kept in place. The trade-offs are infinite, but to make your decision on adoption easier: if
  you've never programmed in Swift or Kotlin, even just a little for both, then go with React
  Native. Otherwise, going native makes life a lot easier with the immense number of tooling for
  native developers.

## Other tools I use

- Notion: for a startup with fewer than 100-200 people, I'd stick with Notion for agility. Beyond
  that, consider Jira + Confluence and keep non-engineers to Notion.
