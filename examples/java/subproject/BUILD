load("@bazel_sonarqube//:defs.bzl", "sq_project", "sonarqube")

sq_project(
    name = "sq_subproject",
    srcs = ["//subproject/src/main/java/com/example:java_srcs"],
    project_key = "com.example.project:subproject",
    project_name = "My Project :: Sub-Project",
    tags = ["manual"],
    targets = ["//subproject/src/main/java/com/example:app"],
    test_reports = ["//:test_reports"],
    test_srcs = ["//subproject/src/test/java/com/example:java_test_srcs"],
    test_targets = ["//subproject/src/test/java/com/example:AppTest"],
    visibility = ["//visibility:public"],
)

sonarqube(
    name = "sonarqube",
    srcs = ["//subproject/src/main/java/com/example:java_srcs"],
    coverage_report = "//:coverage_report",
    project_key = "com.example.project:subproject",
    project_name = "Sub-Project",
    scm_info = ["//:git"],
    tags = ["manual"],
    targets = ["//subproject/src/main/java/com/example:app"],
    test_reports = ["//:test_reports"],
    test_srcs = ["//subproject/src/test/java/com/example:java_test_srcs"],
    test_targets = ["//subproject/src/test/java/com/example:AppTest"],
)