package(default_visibility = ["//adlik_serving:internal"])

load("//adlik_serving:serving.bzl", "serving_cc_library")

serving_cc_library(
    name = "openvino_util",
    srcs = ["openvino_util.cc"],
    hdrs = ["openvino_util.h"],
    deps = [
        "//adlik_serving/framework/domain:dims_list",
        "//adlik_serving/framework/domain:model_config_proto",
        "//adlik_serving/runtime/openvino:ns",
        "@local_config_openvino//:ie_headers",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

serving_cc_library(
    name = "ir_model",
    srcs = ["ir_model.cc"],
    hdrs = [
        "ir_model.h",
    ],
    deps = [
        ":openvino_util",
        "//adlik_serving/framework/domain:model_config_helper",
        "//adlik_serving/runtime/batching:batching_model",
        "//adlik_serving/runtime/batching:composite_batch_processor",
        "//adlik_serving/runtime/openvino:ns",
        "//adlik_serving/runtime/provider:predict_request_provider",
        "//adlik_serving/runtime/provider:predict_response_provider",
        "//cub/log",
        "@local_config_openvino//:extension",
        "@local_config_openvino//:ie_headers",
        "@org_tensorflow//tensorflow/core:lib",
    ],
)

# cc_test(
#     name = "ir_model_test",
#     srcs = ["ir_model_test.cc"],
#     deps = [
#         ":ir_model",
#         "//cub/env/posix",
#         "//cub/log",
#         "@gtest",
#         "@gtest//:gtest_main",
#         "@local_config_openvino//:libinference_engine",
#     ],
# )
