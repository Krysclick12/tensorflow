load("//xla/stream_executor:build_defs.bzl", "stream_executor_friends")
load("@local_tsl//tsl:tsl.bzl", "set_external_visibility")
load("@local_tsl//tsl/platform:rules_cc.bzl", "cc_library")

package(
    default_visibility = ["//visibility:public"],
    licenses = ["notice"],
)

# StreamExecutor clients that can depend on targets defined in stream_executor package.
package_group(
    name = "friends",
    packages = stream_executor_friends(),
)

#===--------------------------------------------------------------------------------------------===#
# StreamExecutor integrations
#===--------------------------------------------------------------------------------------------===#

# Libraries integrating StreamExecutor into framework APIs, e.g. plugging StreamExecutor device
# memory allocator into Tensorflow.

cc_library(
    name = "tf_allocator_adapter",
    srcs = ["tf_allocator_adapter.cc"],
    hdrs = ["tf_allocator_adapter.h"],
    visibility = ["//visibility:public"],
    deps = [
        "//xla/stream_executor",
        "//xla/stream_executor:device_memory",
        "//xla/stream_executor:device_memory_allocator",
        "//xla/stream_executor:platform",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/strings",
        "@local_tsl//tsl/framework:allocator",
        "@local_tsl//tsl/platform:errors",
        "@local_tsl//tsl/platform:statusor",
    ],
)
