# `rules_rss` -- Bazel build rules for RSS

To use these rules, add the following to your `WORKSPACE` file:

```bazel
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "com_github_rules_rss",
    branch = "master",
    remote = "https://github.com/bark-simulator/rules_rss"
)

load("@com_github_rules_rss//rss:rss.bzl", "rss_dependencies")
rss_dependencies()
```

You can then use libaries through the `@ad_rss_lib` repository, for
example `"@ad_rss_lib//:ad_rss_map_integration"`.