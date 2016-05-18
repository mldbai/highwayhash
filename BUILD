# SipHash and HighwayHash: cryptographically-strong pseudorandom functions

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

cc_library(
    name = "vector",
    hdrs = [
        "code_annotation.h",
        "types.h",
        "vec.h",
        "vec2.h",
    ],
)

cc_library(
    name = "sip_hash",
    srcs = ["sip_hash.cc"],
    hdrs = [
        "code_annotation.h",
        "sip_hash.h",
        "state_helpers.h",
        "types.h",
    ],
    visibility = ["//visibility:public"],
)

cc_library(
    name = "sip_tree_hash",
    srcs = ["sip_tree_hash.cc"],
    hdrs = ["sip_tree_hash.h"],
    visibility = ["//visibility:public"],
    deps = [
        ":sip_hash",
        ":vector",
    ],
)

cc_library(
    name = "scalar_sip_tree_hash",
    srcs = ["scalar_sip_tree_hash.cc"],
    hdrs = ["scalar_sip_tree_hash.h"],
    deps = [
        ":sip_hash",
        ":vector",
    ],
)

cc_library(
    name = "highway_tree_hash",
    srcs = ["highway_tree_hash.cc"],
    hdrs = [
        "highway_tree_hash.h",
        "state_helpers.h",
    ],
    visibility = ["//visibility:public"],
    deps = [
        ":vector",
    ],
)

cc_library(
    name = "sse41_highway_tree_hash",
    srcs = ["sse41_highway_tree_hash.cc"],
    hdrs = ["sse41_highway_tree_hash.h"],
    deps = [
        ":vector",
    ],
)

cc_library(
    name = "scalar_highway_tree_hash",
    srcs = ["scalar_highway_tree_hash.cc"],
    hdrs = ["scalar_highway_tree_hash.h"],
    deps = [
        ":vector",
    ],
)

cc_binary(
    name = "sip_hash_main",
    srcs = [
        "sip_hash_main.cc",
    ],
    deps = [
        ":highway_tree_hash",
        ":scalar_highway_tree_hash",
        ":scalar_sip_tree_hash",
        ":sip_hash",
        ":sip_tree_hash",
        ":sse41_highway_tree_hash",
        ":vector",
    ],
)
