# Automatic Environment Variables with `direnv`

`direnv` is a shell extension that automatically loads and
unloads environment variables when you enter or leave a
directory.

💡 Instead of manually exporting environment variables or
sourcing `.env` files, `direnv` hooks into your shell and
handles it seamlessly based on a `.envrc` file in your
project directory.

## Basic Usage

Create an `.envrc` file in your project directory:

```sh
export DATABASE_URL="postgres://localhost:5432/myapp_dev"
export SECRET_KEY="dev-only-secret"
export RAILS_ENV="development"
```

The first time `direnv` detects a new or changed `.envrc`,
it blocks loading until you explicitly allow it:

```plaintext
direnv: error /path/to/project/.envrc is blocked.
Run `direnv allow` to approve its content
```

```sh
direnv allow
```

💡 This security mechanism prevents untrusted `.envrc`
files from running automatically. You must approve each
file and re-approve after any changes.

## How it works

When you `cd` into a directory with an `.envrc`, `direnv`
automatically exports the variables:

```plaintext
$ cd ~/projects/myapp
direnv: loading ~/projects/myapp/.envrc
direnv: export +DATABASE_URL +SECRET_KEY +RAILS_ENV

$ echo $DATABASE_URL
postgres://localhost:5432/myapp_dev
```

When you leave the directory, the variables are unloaded:

```plaintext
$ cd ~
direnv: unloading
```

## Subdirectory Inheritance

`direnv` searches up the directory tree, so an `.envrc`
in a parent directory applies to all subdirectories. This
is useful for organizing work and personal projects with
different credentials:

```plaintext
~/code/
├── work/
│   ├── .envrc          # AWS_PROFILE="work-account"
│   └── project-a/      # inherits work credentials
└── personal/
    ├── .envrc          # AWS_PROFILE="personal"
    └── my-project/     # inherits personal credentials
```

```plaintext
$ cd ~/code/work/project-a
direnv: loading ~/code/work/.envrc
direnv: export +AWS_PROFILE

$ echo $AWS_PROFILE
work-account

$ cd ~/code/personal/my-project
direnv: loading ~/code/personal/.envrc
direnv: export ~AWS_PROFILE

$ echo $AWS_PROFILE
personal
```

💡 No need to duplicate `.envrc` files in every project.
Place shared variables at the parent level and they apply
to all subdirectories automatically.

## Why use this?

- Keep environment variables scoped to the project that
  needs them
- Avoid polluting your global shell environment
- Share configuration with teammates via `.envrc.example`
  while keeping `.envrc` in `.gitignore`
- No need to remember to source files or manage shell
  profiles per project

## Resources

- [direnv.net](https://direnv.net/)

🎉 Happy coding!
