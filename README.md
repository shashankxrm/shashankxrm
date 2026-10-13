<h1 align="center">Shashank Reddy</h1>

<p align="center">
Distributed Systems &nbsp;·&nbsp; Backend &nbsp;·&nbsp; Golang Microservices &nbsp;·&nbsp; Cloud &amp; DevOps<br/>
Go, C++ &amp; Java, gRPC, event-driven architecture<br/>
Software Engineer &nbsp;·&nbsp; Contributor to CNCF-hosted projects
</p>

<p align="center">
<a href="https://shashankxrm.vercel.app/">Portfolio</a> &nbsp;·&nbsp;
<a href="https://www.linkedin.com/in/shashankxrm/">LinkedIn</a> &nbsp;·&nbsp;
<a href="https://shashanksblog.hashnode.dev">Blog</a> &nbsp;
    <!-- ·&nbsp; -->
<!-- <a href="https://x.com/">X</a> -->
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white" alt="Go" />
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++" />
  <img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/-Distributed%20Systems-1d4ed8?style=flat-square" alt="Distributed Systems" />
  <img src="https://img.shields.io/badge/-Observability-7c3aed?style=flat-square" alt="Observability" />
  <img src="https://img.shields.io/badge/-Tracing-0891b2?style=flat-square" alt="Tracing" />
  <img src="https://img.shields.io/badge/-Metrics%20Cardinality-ea580c?style=flat-square" alt="Metrics Cardinality" />
  <img src="https://img.shields.io/badge/-Concurrency-16a34a?style=flat-square" alt="Concurrency" />
  <img src="https://img.shields.io/badge/-Spec%20Compliance-475569?style=flat-square" alt="Spec Compliance" />
</p>

---


## Open Source Work

<table align="center">
  <tr>
    <td><a href="https://github.com/pulls?q=is%3Apr+author%3Ashashankxrm+org%3Aopen-telemetry"><img src="https://img.shields.io/badge/OTel%20C%2B%2B-425CC7?style=for-the-badge&logo=opentelemetry&logoColor=white" /></a></td>
    <td>Spec-compliant config defaults, service resource detector, Entity support, pkg-config packaging</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trickstercache/trickster/pulls?q=is%3Apr+author%3Ashashankxrm"><img src="https://img.shields.io/badge/Trickster-0F766E?style=for-the-badge" /></a></td>
    <td>IP access control lists and rate limiting for the v2.2 proxy</td>
  </tr>
  <tr>
    <td><a href="https://github.com/keycloak/keycloak/pulls?q=is%3Apr+author%3Ashashankxrm"><img src="https://img.shields.io/badge/Keycloak-4D4D4D?style=for-the-badge&logo=keycloak&logoColor=white" /></a></td>
    <td>OID4VCI client-scope fixes, mdoc E2E coverage, CIMD client-policy fix</td>
  </tr>
  <tr>
    <td><a href="https://github.com/pulls?q=is%3Apr+author%3Ashashankxrm+org%3Aknative+org%3Atektoncd"><img src="https://img.shields.io/badge/Knative%20%C2%B7%20Tekton-0865AD?style=for-the-badge&logo=knative&logoColor=white" /></a></td>
    <td>StatefulSet ordinal leader election: fail fast instead of orphaning buckets</td>
  </tr>
</table>

<details>
<summary><b>Pull requests</b> &nbsp;(✅ merged · 🟡 open)</summary>

<br/>

**OpenTelemetry C++**

| PR | What it did |
|---|---|
| ✅ [#4440](https://github.com/open-telemetry/opentelemetry-cpp/pull/4440) Set schema default values for all parameters | Aligned declarative-config defaults with the OTel configuration schema. Before this, an omitted `trace_id_ratio_based` ratio dropped every trace (0.0 vs 1.0), and limits and export intervals used legacy values |
| ✅ [#4450](https://github.com/open-telemetry/opentelemetry-cpp/pull/4450) Add the service resource detector and builder | Implemented the missing built-in `service` detector: `service.name` from `OTEL_SERVICE_NAME` with the spec fallback, and a UUID `service.instance.id`, on Linux, macOS and Windows |
| ✅ [#4528](https://github.com/open-telemetry/opentelemetry-cpp/pull/4528) Clean up pkg-config install methods and add tests | Moved `.pc` generation out of about 50 call sites into the component install path, with consumer tests that build against the installed `.pc` files |
| 🟡 [#4490](https://github.com/open-telemetry/opentelemetry-cpp/pull/4490) Add Entity support to Resource | Step 1 of entity propagation (spec 1.60): a public SDK `Entity` value type with tests |

**Trickster**

| PR | What it did |
|---|---|
| ✅ [#1171](https://github.com/trickstercache/trickster/pull/1171) Support IP access control lists | Named `ip_acls` that allow or refuse clients by resolved client IP or socket peer, on listeners, backends and paths, including Kubernetes-generated routes, so operators don't need a second proxy |
| ✅ [#1190](https://github.com/trickstercache/trickster/pull/1190) Support rate limiting | Named `rate_limiters` (sliding window, per key) for HTTP and TCP/UDP, layered on listeners and routes with shared bucket tables and metrics |

**Keycloak**

| PR | What it did |
|---|---|
| ✅ [#52209](https://github.com/keycloak/keycloak/pull/52209) Allow unsetting optional OID4VCI client scope attributes | Fixed admin UI and JPA so cleared OID4VCI credential-scope fields actually unset, with backend and Playwright regression tests |
| ✅ [#52453](https://github.com/keycloak/keycloak/pull/52453) Enable mdoc in Admin UI E2E tests | Turned on the mdoc feature in the Admin UI end-to-end test suite |
| 🟡 [#52469](https://github.com/keycloak/keycloak/pull/52469) Fix ClientUpdaterSource conditions for CIMD | Groups and roles client-policy conditions threw on CIMD contexts and broke CIMD login. They now skip those contexts instead of erroring |

**Knative · Tekton**

| PR | What it did |
|---|---|
| 🟡 [knative/pkg#3393](https://github.com/knative/pkg/pull/3393) Fix StatefulSet ordinal election leaving buckets unowned | With 8 buckets and 4 replicas, buckets 4–7 were never reconciled. pkg now requires `STATEFUL_REPLICA_COUNT`, enforces `replicas == buckets` and fails instead of silently falling back to leases |
| 🟡 [tektoncd/operator#4124](https://github.com/tektoncd/operator/pull/4124) Inject `STATEFUL_REPLICA_COUNT` for ordinal election | The companion fix: the operator injects the final rendered replica count into Pipeline, Chains and Results so pkg can validate it |

</details>

---

## Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=go,java,cpp,ts,py,postgres,redis,mongodb&perline=8" height="55" />
</p>
<p align="center">
  <img src="https://skillicons.dev/icons?i=kubernetes,docker,terraform,grafana,prometheus,githubactions,linux,aws&perline=8" height="55" />
</p>

---
## Contribution graph

<p align="center">
  <img src="https://raw.githubusercontent.com/shashankxrm/shashankxrm/main/profile-3d-contrib/profile-night-green.svg" alt="3D contribution graph" />
</p>

---

## GitHub Stats

<p align="center">
  <img src="https://github-readme-stats-shashank.vercel.app/api?username=shashankxrm&show_icons=true&locale=en&theme=radical" alt="GitHub stats" />
</p>
<p align="center">
  <img src="https://streak-stats.demolab.com/?user=shashankxrm&theme=radical" alt="Streak stats" />
</p>



