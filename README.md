# 20G

This is a project following along the [20 Games Challenge](https://20_games_challenge.gitlab.io/) 
done in the [Godot](https://godotengine.org/) game engine

Each game is independent and lives on its own repo as a git submodule. 

## Rules 

1. **No tutorials are allowed**: making a game following a tutorial would render this whole project useless.
2. **Constrain yourself**: set feature and time limits *(20hr recommended)*, polishing can alwas be done later but the idea is to hava a working game by the end of it.
3. **Be flexible**: make rough plans and change or update along the way

## Games

| # | Title | Genre | Description |
|---|-------|-------|-------------|
| 1 | TBD   | TBD   | TBD         |

## Monorepo management

Cloning this whole project

```bash
git clone --recurse-submodules https://github.com/Diomeh/20g
```

***

Adding a game as a submodule

```bash
git submodule add <repo-url> games/<name> 
git submodule init
git submodule update
git add .gitmodules games/<name>
git commit -m "feat: add game <name>"
```

***

Updating monorepo

```bash
git submodule update --init --recursive
```

Or 

```bash
git submodule update --remote --merge
```

***

Removing a game

```bash
git submodule deinit -f games/<name>
rm -rf games/<name> .git/modules/games/<name>
git rm -f games/<name>
git commit -m "feat: remove game <name>"
```

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.

## Author

[David Urbina](https://github.com/Diomeh)

## Conventions

This project follws both the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/#summary)
and [Semantic Versioning](https://semver.org/) specifications.

Semantic versioning is ensured by leveraging conventional commits.

The commit message should be structured as follows:

```plaintext
{type}[optional scope]: {description}

[optional body]

[optional footer(s)]
```

Where `type` is one of the following:

| Type              | Description                                                                                             | Example Commit Message                            |
| ----------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| `fix`             | Patches a bug in your codebase (correlates with PATCH in Semantic Versioning)                           | `fix: correct typo in README`                     |
| `feat`            | Introduces a new feature to the codebase (correlates with MINOR in Semantic Versioning)                 | `feat: add new user login functionality`          |
| `BREAKING CHANGE` | Introduces a breaking API change (correlates with MAJOR in Semantic Versioning)                         | `feat!: drop support for Node 8`                  |
| `build`           | Changes that affect the build system or external dependencies                                           | `build: update dependency version`                |
| `chore`           | Other changes that don't modify src or test files                                                       | `chore: update package.json scripts`              |
| `ci`              | Changes to CI configuration files and scripts                                                           | `ci: add CircleCI config`                         |
| `docs`            | Documentation only changes                                                                              | `docs: update API documentation`                  |
| `style`           | Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc.) | `style: fix linting errors`                       |
| `refactor`        | Code change that neither fixes a bug nor adds a feature                                                 | `refactor: rename variable for clarity`           |
| `perf`            | Code change that improves performance                                                                   | `perf: reduce size of image files`                |
| `test`            | Adding missing tests or correcting existing tests                                                       | `test: add unit tests for new feature`            |
| Custom Types      | Any other type defined by the project for its specific needs                                            | `security: address vulnerability in dependencies` |

For more information, refer to the [Conventional Commits Specification](https://www.conventionalcommits.org/en/v1.0.0/).