load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository", "new_git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

all_content = """filegroup(name = "all", srcs = glob(["**"]), visibility = ["//visibility:public"])"""

http_archive(
    name = "rules_cc",
    sha256 = "49c1a79d64d04f3fa6f98e5738906265943db094c9b6e66dbe844dd576f6faf7",
    strip_prefix = "rules_cc-master",
    urls = ["https://github.com/bazelbuild/rules_cc/archive/master.zip"],
)

git_repository(
    name = "googletest",
    commit = "703bd9caab50b139428cea1aaff9974ebee5742e",
    remote = "https://github.com/google/googletest",
    shallow_since = "1570114335 -0400",
)

git_repository(
    name = "com_google_absl",
    commit = "c51510d1d87ebce8615ae1752fd5aca912f6cf4c",
    remote = "https://github.com/abseil/abseil-cpp.git",
    shallow_since = "1587584588 -0400",
)

git_repository(
    name = "glog",
    commit = "96a2f23dca4cc7180821ca5f32e526314395d26a",
    remote = "https://github.com/google/glog.git",
    shallow_since = "1553223106 +0900",
)

git_repository(
    name = "com_github_gflags_gflags",
    commit = "e171aa2d15ed9eb17054558e0b3a6a413bb01067",
    remote = "https://github.com/gflags/gflags.git",
    shallow_since = "1541971260 +0000",
)

http_archive(
    name = "rules_proto",
    sha256 = "602e7161d9195e50246177e7c55b2f39950a9cf7366f74ed5f22fd45750cd208",
    strip_prefix = "rules_proto-97d8af4dc474595af3900dd85cb3a29ad28cc313",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_proto/archive/97d8af4dc474595af3900dd85cb3a29ad28cc313.tar.gz",
        "https://github.com/bazelbuild/rules_proto/archive/97d8af4dc474595af3900dd85cb3a29ad28cc313.tar.gz",
    ],
)

# Rule repository
http_archive(
    name = "rules_foreign_cc",
    sha256 = "f358144776d3dfc5a928ef32a0e4fbe93c99b55772d70cca77a6478e34d96aa7",
    strip_prefix = "rules_foreign_cc-master",
    url = "https://github.com/bazelbuild/rules_foreign_cc/archive/master.zip",
)

load("@rules_foreign_cc//:workspace_definitions.bzl", "rules_foreign_cc_dependencies")

rules_foreign_cc_dependencies()

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

rules_proto_dependencies()

rules_proto_toolchains()
