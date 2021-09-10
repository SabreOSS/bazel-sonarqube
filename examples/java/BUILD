filegroup(
    name = "git",
    srcs = glob(
        [".git/**"],
        exclude = [".git/**/*[*"],  # gitk creates temp files with []
    ),
    tags = ["manual"],
    visibility = ["//visibility:public"],
)

filegroup(
    name = "coverage_report",
    srcs = ["bazel-out/_coverage/_coverage_report.dat"],  # Created manually
    tags = ["manual"],
    visibility = ["//visibility:public"],
)

filegroup(
    name = "test_reports",
    srcs = glob(["bazel-testlogs/**/test.xml"]),  # Created manually
    tags = ["manual"],
    visibility = ["//visibility:public"],
)

load("@bazel_sonarqube//:defs.bzl", "sonarqube")

sonarqube(
    name = "sonarqube1",
    srcs = [],
    coverage_report = ":coverage_report",
    modules = {
        "//subproject:sq_subproject": "subproject",
        "//another-subproject:sq_subproject": "another-subproject",
    },
    project_key = "com.example.project:modularized-project",
    project_name = "Modularized Project",
    scm_info = [":git"],
    tags = ["manual"],
    targets = [],
)

sonarqube(
    name = "sonarqube2",
    srcs = [
        "//subproject/src/main/java/com/example:java_srcs",
        "//another-subproject/src/main/java/com/example:java_srcs",
    ],
    coverage_report = "//:coverage_report",
    project_key = "com.example.project:full-project",
    project_name = "Full project",
    scm_info = ["//:git"],
    tags = ["manual"],
    targets = [
        "//subproject/src/main/java/com/example:app",
        "//another-subproject/src/main/java/com/example:app",
    ],
    test_reports = ["//:test_reports"],
    test_srcs = [
        "//subproject/src/test/java/com/example:java_test_srcs",
        "//another-subproject/src/test/java/com/example:java_test_srcs",
    ],
    test_targets = [
        "//subproject/src/test/java/com/example:AppTest",
        "//another-subproject/src/test/java/com/example:AppTest",
    ],
)