load("@bazel_sonarqube//:defs.bzl", "sq_project", "sonarqube")

sq_project(
    name = "sq_subproject",
    srcs = ["//another-subproject/src/main/java/com/example:java_srcs"],
    project_key = "com.example.project:another-subproject",
    project_name = "My Project :: Another-Sub-Project",
    tags = ["manual"],
    targets = ["//another-subproject/src/main/java/com/example:app"],
    test_reports = ["//:test_reports"],
    test_srcs = ["//another-subproject/src/test/java/com/example:java_test_srcs"],
    test_targets = ["//another-subproject/src/test/java/com/example:AppTest"],
    visibility = ["//visibility:public"],
)

sonarqube(
    name = "sonarqube",
    srcs = ["//another-subproject/src/main/java/com/example:java_srcs"],
    coverage_report = "//:coverage_report",
    project_key = "com.example.project:another-subproject",
    project_name = "Another Sub-Project",
    scm_info = ["//:git"],
    tags = ["manual"],
    targets = ["//another-subproject/src/main/java/com/example:app"],
    test_reports = ["//:test_reports"],
    test_srcs = ["//another-subproject/src/test/java/com/example:java_test_srcs"],
    test_targets = ["//another-subproject/src/test/java/com/example:AppTest"],
    visibility = ["//visibility:public"],
)