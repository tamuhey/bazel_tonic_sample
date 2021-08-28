load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_rust",
    sha256 = "631094fe3a45d1ff765a0bc6acd229e4c6e02cb9770d65d21012f3ff493e53da",
    strip_prefix = "rules_rust-a366b7614e0072d7f71e413dd49a94bde69faa96",
    urls = [
        "https://github.com/bazelbuild/rules_rust/archive/a366b7614e0072d7f71e413dd49a94bde69faa96.tar.gz",
    ],
)

load("@rules_rust//rust:repositories.bzl", "rust_repositories")

rust_repositories()

load("//cargo:crates.bzl", "raze_fetch_remote_crates")

raze_fetch_remote_crates()

# protoc
http_archive(
    name = "protobuf",
    build_file_content = """exports_files(["bin/protoc"])""",
    sha256 = "d4246a5136cf9cd1abc851c521a1ad6b8884df4feded8b9cbd5e2a2226d4b357",
    urls = [
        "https://github.com/protocolbuffers/protobuf/releases/download/v3.17.3/protoc-3.17.3-linux-x86_64.zip",
    ],
)
