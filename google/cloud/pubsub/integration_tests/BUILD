# Copyright 2020 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # Apache 2.0

load(":pubsub_client_integration_tests.bzl", "pubsub_client_integration_tests")
load(":pubsub_client_install_tests.bzl", "pubsub_client_install_tests")

[cc_test(
    name = test.replace("/", "_").replace(".cc", ""),
    timeout = "long",
    srcs = [test],
    tags = [
        "integration-test",
    ],
    deps = [
        "//google/cloud:google_cloud_cpp_common",
        "//google/cloud/pubsub:pubsub_client",
        "//google/cloud/testing_util:google_cloud_cpp_testing",
        "@com_google_googletest//:gtest_main",
    ],
) for test in pubsub_client_integration_tests]

[cc_test(
    name = test.replace("/", "_").replace(".cc", ""),
    srcs = [test],
    tags = [
        "integration-test",
    ],
    deps = [
        "//google/cloud:google_cloud_cpp_common",
        "//google/cloud/pubsub:pubsub_client",
    ],
) for test in pubsub_client_install_tests]
