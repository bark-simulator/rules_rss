load("@com_github_rules_rss//rss:custom_rules.bzl", "header_template")

header_template(
    name = "proj_config",
    extension = ".h",
    template = "src/proj_config.h.in",
    visibility = ["//visibility:public"],
)

cc_library(
    name = "proj",
    srcs = glob(
        [
            "src/**/*.cpp",
            "src/**/*.c",
        ],
        exclude = [
            "src/apps/*.cpp",
            "src/tests/*.cpp",
        ],
    ),
    hdrs = glob(
        [
            "include/**/*.hpp",
            "src/**/*.h",
            "src/**/*.hpp",
        ],
        exclude = ["src/apps/*.h"],
    ) + [
        "proj_config.h",
    ],
    includes = [
        ".",
        "include",
        "src",
    ],
    linkopts = [
        "-lsqlite3",
    ],
    visibility = ["//visibility:public"],
    deps = [
        ":proj_config",
        "@boost//:algorithm",
        "@boost//:array",
        "@boost//:functional",
        "@boost//:geometry",
        "@boost//:lexical_cast",
        "@boost//:math",
        "@boost//:program_options",
        "@gtest",
    ],
)
