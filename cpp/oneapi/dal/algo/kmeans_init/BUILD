package(default_visibility = ["//visibility:public"])
load("@onedal//dev/bazel:dal.bzl",
    "dal_module",
    "dal_test_suite",
)

dal_module(
    name = "kmeans_init",
    auto = True,
    dal_deps = [
        "@onedal//cpp/oneapi/dal:core",
        "@onedal//cpp/oneapi/dal/backend/primitives:rng",
        "@onedal//cpp/oneapi/dal/backend/primitives:common",
        "@onedal//cpp/oneapi/dal/backend/primitives:distance",
        "@onedal//cpp/oneapi/dal/backend/primitives:selection",
        "@onedal//cpp/oneapi/dal/backend/primitives:placement",
        "@onedal//cpp/oneapi/dal/backend/primitives:reduction",
    ],
    extra_deps = [
        "@onedal//cpp/daal/src/algorithms/kmeans:kernel",
    ]
)

dal_test_suite(
    name = "interface_tests",
    framework = "catch2",
    hdrs = glob([
        "test/*.hpp",
    ]),
    srcs = glob([
        "test/*.cpp",
    ]),
    dal_deps = [
        ":kmeans_init",
    ],
)

dal_test_suite(
    name = "tests",
    tests = [
        ":interface_tests",
    ],
)
