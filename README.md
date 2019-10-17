# `rules_stb` -- Bazel build rules for STB

To use these rules, add the following to your `WORKSPACE` file:

```python
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "stb",
    init_submodules = True,
    branch = "master",
    remote = "https://github.com/nitronoid/rules_stb"
)
```
You can then use the `stb` libraries via the `@stb` label.
For example you can add `@stb//:image` to your `deps` to use `stb_image`.
