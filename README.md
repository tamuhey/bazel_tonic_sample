```
$ cargo raze
$ bazel build ... # fail
```

Edit `./cargo/remote/BUILD.tonic-health-0.4.1.bazel` and add the following arguments to `:tonic_health_build_script`:

```
cargo_build_script(
    name = "tonic_health_build_script",
    build_script_env = {
        "PROTOC": "$(location @//:protoc)" # add protoc location here,
    },
    ...
    data = glob(["**"]) + ["@//:protoc"] # add protoc data here,
)
```

Now build would pass:

```
$ bazel build ... # ok
```
