load("@rules_license//rules:license.bzl", "license")
load("@rules_license//rules:license_kind.bzl", "license_kind")
load("@rules_rust//rust:defs.bzl", "rust_proc_macro")

package(
    default_applicable_licenses = [":license"],
    default_visibility = ["//visibility:public"],
)

license(
    name = "license",
    license_kinds = [
        ":SPDX-license-identifier-Apache-2.0",
        ":SPDX-license-identifier-MIT",
    ],
    license_text = "LICENSE-APACHE",
    visibility = [":__subpackages__"],
)

license_kind(
    name = "SPDX-license-identifier-Apache-2.0",
    conditions = ["notice"],
    url = "https://spdx.org/licenses/Apache-2.0.html",
)

license_kind(
    name = "SPDX-license-identifier-MIT",
    conditions = ["notice"],
    url = "",
)

rust_proc_macro(
    name = "zerocopy-derive",
    srcs = glob(["**/*.rs"]),
    edition = "2018",
    deps = [
        # This should map to repo checked out from Android third party project
        # "platform/external/rust/crates/proc-macro2". Similar for the rest of the dependencies
        # below.
        "@proc-macro2",
        # Map to project repo "platform/external/rust/crates/quote".
        "@quote",
        # Map to project repo "platform/external/rust/crates/syn".
        "@syn",
    ],
)
