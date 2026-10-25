<h1 align="center">Open Source Contributions</h1>

<p align="center">
Merged upstream work across CNCF projects: registry security, proxy reliability, telemetry SDKs and test coverage.
</p>

<p align="center">
<b>18 merged PRs</b> &nbsp;·&nbsp; <b>5 CNCF projects</b> &nbsp;·&nbsp; last updated 2026-10-25
</p>

<p align="center"><sub>⭐ = core contribution, the ones I go deepest on &nbsp;·&nbsp; dates are merge dates (UTC)</sub></p>

---

## At a glance

| Project | What it is | Lang | Merged |
|---|---|---|:-:|
| [ORAS](#oras--oras-go) | OCI registry client library | Go | 8 |
| [Trickster](#trickster) | HTTP reverse-proxy cache for time-series DBs | Go | 2 |
| [OpenTelemetry C++](#opentelemetry-c) | OpenTelemetry API and SDK for C++ | C++ | 3 |
| [Kepler](#kepler) | Kubernetes energy/power exporter | Go | 3 |
| [Keycloak](#keycloak) | Identity and access management | Java · TS | 2 |

---

## ORAS · oras-go

> [oras-go](https://github.com/oras-project/oras-go) is the Go library for pushing and pulling OCI artifacts to container registries. The ORAS CLI and other tools build on it.

| PR | What & why | Issue | Merged | Release |
|---|---|:-:|:-:|:-:|
| ⭐ [#1635](https://github.com/oras-project/oras-go/pull/1635) | **Configurable bearer-realm denylist.** Blocks token realms at loopback, link-local and cloud-metadata addresses (SSRF), with a strict mode for private ranges, and fixes split-host internal registries broken by v2.6.4. Set per registry via `BlockedRealmPrefixes` | [#1632](https://github.com/oras-project/oras-go/issues/1632) | 2026-10-21 | v3.0.0-rc.3 |
| ⭐ [#1662](https://github.com/oras-project/oras-go/pull/1662) | **Denylist in `registries.conf`.** Exposes the same policy as a `blocked-realm-prefixes` config key, inherited by mirror clients | [#1634](https://github.com/oras-project/oras-go/issues/1634) | 2026-10-22 | unreleased |
| ⭐ [#1628](https://github.com/oras-project/oras-go/pull/1628) | **Default copy concurrency 3 → 8.** About 2.2× faster (172.3 → 80.1 ms) on my 42-node, 5 ms-latency benchmark added in the PR | [#1622](https://github.com/oras-project/oras-go/issues/1622) | 2026-10-19 | v3.0.0-rc.3 |
| ⭐ [#1612](https://github.com/oras-project/oras-go/pull/1612) | **Verify `Docker-Content-Digest` on monolithic blob push.** Catches a registry that stored different bytes than were sent | [#1609](https://github.com/oras-project/oras-go/issues/1609) | 2026-10-17 | v3.0.0-rc.3 |
| ⭐ [#1615](https://github.com/oras-project/oras-go/pull/1615) | **Accept a registry-chosen digest algorithm on tag pushes**, while still verifying the content | [#1608](https://github.com/oras-project/oras-go/issues/1608) | 2026-10-18 | v3.0.0-rc.3 |
| [#1643](https://github.com/oras-project/oras-go/pull/1643) | v2 backport: match `FilterArtifactType` against an image manifest's `artifactType` | [#1641](https://github.com/oras-project/oras-go/issues/1641) | 2026-10-20 | v2.7.0 |
| [#1685](https://github.com/oras-project/oras-go/pull/1685) | Log every retry attempt in `ClientBuilder`, not just the final one | [#1680](https://github.com/oras-project/oras-go/issues/1680) | 2026-10-24 | unreleased |
| [#1692](https://github.com/oras-project/oras-go/pull/1692) | Reject unbracketed IPv6 registry hosts in references | [#1689](https://github.com/oras-project/oras-go/issues/1689) | 2026-10-24 | unreleased |

---

## Trickster

> [Trickster](https://github.com/trickstercache/trickster) is an HTTP reverse-proxy cache and accelerator for time-series databases like Prometheus.

| PR | What & why | Issue | Merged |
|---|---|:-:|:-:|
| ⭐ [#1190](https://github.com/trickstercache/trickster/pull/1190) | **Sliding-window rate limiting.** Named, per-key `rate_limiters` for HTTP and TCP/UDP, layered on listeners and routes, with shared bucket tables and metrics | [#1147](https://github.com/trickstercache/trickster/issues/1147) | 2026-10-11 |
| [#1171](https://github.com/trickstercache/trickster/pull/1171) | IP access control lists: named `ip_acls` that allow or deny clients on listeners, backends and paths, so operators don't need a second proxy | [#1148](https://github.com/trickstercache/trickster/issues/1148) | 2026-10-03 |

---

## OpenTelemetry C++

> [opentelemetry-cpp](https://github.com/open-telemetry/opentelemetry-cpp) is the C++ implementation of the OpenTelemetry API and SDK for traces, metrics and logs.

| PR | What & why | Issue | Merged |
|---|---|:-:|:-:|
| ⭐ [#4450](https://github.com/open-telemetry/opentelemetry-cpp/pull/4450) | **Service resource detector and builder.** `service.name` from `OTEL_SERVICE_NAME` with the spec fallback, plus a UUID `service.instance.id` cached per PID (fork-safe), on Linux, macOS and Windows | [#4414](https://github.com/open-telemetry/opentelemetry-cpp/issues/4414) | 2026-08-22 |
| [#4440](https://github.com/open-telemetry/opentelemetry-cpp/pull/4440) | Schema default values for all declarative-config parameters. An omitted sampler ratio used to drop every trace (0.0 instead of 1.0) | [#4432](https://github.com/open-telemetry/opentelemetry-cpp/issues/4432) | 2026-08-17 |
| [#4528](https://github.com/open-telemetry/opentelemetry-cpp/pull/4528) | Moved pkg-config generation from about 50 call sites into the component install path, with consumer tests against the installed `.pc` files | [#4503](https://github.com/open-telemetry/opentelemetry-cpp/issues/4503) | 2026-10-10 |

---

## Kepler

> [Kepler](https://github.com/sustainable-computing-io/kepler) is a Kubernetes exporter that estimates and exposes energy and power use by node, pod and process.

| PR | What & why | Issue | Merged |
|---|---|:-:|:-:|
| [#2607](https://github.com/sustainable-computing-io/kepler/pull/2607) | Test coverage for `PowerMonitor` shutdown and refresh error paths | [#2605](https://github.com/sustainable-computing-io/kepler/issues/2605) | 2026-10-22 |
| [#2645](https://github.com/sustainable-computing-io/kepler/pull/2645) | Native Go fuzz tests for the resource and DCGM parsers | [#2615](https://github.com/sustainable-computing-io/kepler/issues/2615) | 2026-10-23 |
| [#2653](https://github.com/sustainable-computing-io/kepler/pull/2653) | Upgraded the toolchain to Go 1.27 | [#2649](https://github.com/sustainable-computing-io/kepler/issues/2649) | 2026-10-25 |

---

## Keycloak

> [Keycloak](https://github.com/keycloak/keycloak) is an open-source identity and access management server (SSO, OAuth 2.0 / OIDC, verifiable credentials).

| PR | What & why | Issue | Merged |
|---|---|:-:|:-:|
| [#52209](https://github.com/keycloak/keycloak/pull/52209) | Optional OID4VCI client-scope attributes can now be unset: fixed the Admin UI and `ClientScopeAdapter`, which stored `""` instead of removing the attribute, with backend and Playwright tests | [#52190](https://github.com/keycloak/keycloak/issues/52190) | 2026-09-02 |
| [#52453](https://github.com/keycloak/keycloak/pull/52453) | Enabled the mdoc feature in the Admin UI end-to-end test suite | [#52452](https://github.com/keycloak/keycloak/issues/52452) | 2026-09-04 |

---

## In review

- 🟡 **OpenTelemetry C++** [#4490](https://github.com/open-telemetry/opentelemetry-cpp/pull/4490): add `Entity` support to `Resource` (step 1 of entity propagation)
- 🟡 **Keycloak** [#52469](https://github.com/keycloak/keycloak/pull/52469): fix `ClientUpdaterSource` conditions that broke CIMD client events
- 🟡 **Knative** [knative/pkg#3393](https://github.com/knative/pkg/pull/3393): StatefulSet ordinal election fails fast instead of leaving buckets unowned
- 🟡 **Tekton** [tektoncd/operator#4124](https://github.com/tektoncd/operator/pull/4124): inject `STATEFUL_REPLICA_COUNT` so ordinal election can validate replicas

<p align="center"><sub>All merged PRs: <a href="https://github.com/pulls?q=is%3Apr+author%3Ashashankxrm+is%3Amerged">github.com/pulls?q=author:shashankxrm is:merged</a></sub></p>
