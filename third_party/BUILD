# Description:
#   Thirdparty dependencies indirection for bazel.
package(default_visibility = ["//:__subpackages__"])

# Apache2
licenses(["notice"])

# Direct dependencies for compiling java src code of the closure jsinterop generator.
# These targets don't need to be public.
java_plugin(
    name = "auto_annotation_plugin",
    processor_class = "com.google.auto.value.processor.AutoAnnotationProcessor",
    deps = ["@com_google_auto_value"],
)

java_plugin(
    name = "auto_value_plugin",
    processor_class = "com.google.auto.value.processor.AutoValueProcessor",
    deps = ["@com_google_auto_value"],
)

java_library(
    name = "auto_value",
    exported_plugins = [
        ":auto_annotation_plugin",
        ":auto_value_plugin",
    ],
    exports = ["@com_google_auto_value"],
)

java_library(
    name = "jscomp",
    exports = ["@com_google_javascript_closure_compiler"],
)

java_library(
    name = "args4j",
    exports = ["@args4j"],
)

java_library(
    name = "jsr305_annotations",
    exports = ["@com_google_code_findbugs_jsr305"],
)

java_library(
    name = "guava",
    exports = ["@com_google_guava"],
)

alias(
    name = "gwt-jsinterop-annotations",
    actual = "@com_google_j2cl//:jsinterop-annotations",
)

alias(
    name = "gwt-jsinterop-annotations-j2cl",
    actual = "@com_google_j2cl//:jsinterop-annotations-j2cl",
)

# Dependencies used in the jsinterop_generator skylark rules.
# These dependencies need to be publicly visible in order to allow any other repo to use the
# jsinterop generator rule.

java_binary(
    name = "google_java_format",
    main_class = "com.google.googlejavaformat.java.Main",
    runtime_deps = ["@com_google_google_java_format//jar"],
    visibility = ["//visibility:public"],
)

alias(
    name = "jar",
    actual = "@bazel_tools//tools/jdk:jar",
    visibility = ["//visibility:public"],
)

alias(
    name = "jdk",
    actual = "@bazel_tools//tools/jdk:current_java_runtime",
    visibility = ["//visibility:public"],
)

alias(
    name = "jsinterop-base",
    actual = "@com_google_jsinterop_base//:jsinterop-base",
    visibility = ["//javatests:__subpackages__"],
)

alias(
    name = "jsinterop-base-j2cl",
    actual = "@com_google_jsinterop_base//:jsinterop-base-j2cl",
    visibility = ["//javatests:__subpackages__"],
)
