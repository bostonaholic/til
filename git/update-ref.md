# git update-ref

`git update-ref` is a command that updates the value of a reference in the repository.

💡 This is a low-level command that directly manipulates refs without creating reflog entries or performing safety checks. It's useful for scripting or creating custom references.

## Creating named references

```sh
git update-ref refs/heads/current HEAD
```

This command updates the `refs/heads/current` reference to point to the current HEAD.

```sh
git update-ref refs/heads/previous HEAD~1
```

This command updates the `refs/heads/previous` reference to point to the previous commit.

The ref name can be used in a `git checkout` command to switch to that commit.

```sh
git checkout previous
```

## Deleting references

```sh
git update-ref -d refs/heads/previous
```

💡 Use the `-d` flag to delete a reference safely.

## Why use this?

- Create bookmarks to specific commits without creating branches
- Implement custom workflows or Git automation scripts
- Manipulate refs in a programmatic way

🎉 Happy coding!
