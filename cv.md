# Asu Singh

India | +91-9910521365 | itsasusingh@gmail.com | [linkedin.com/in/asusingh](https://linkedin.com/in/asusingh) | [github.com/Enixes](https://github.com/Enixes/) | [Portfolio](https://enixes.vercel.app)

## Summary

Senior Software Engineer with 6+ years building production systems for demanding enterprise clients. Deep expertise in Java, multithreading, performance optimisation, and production reliability. Independently built an agentic AI assistant using free NVIDIA models and AI coding agents — prototype to deployed 24/7 system. Combines engineering discipline with AI capability to deliver reliable, high-impact solutions.

## Skills

- Languages: Java 8+, Python, C#, JavaScript, SQL
- Backend & APIs: Spring Boot, microservices, REST APIs, Hibernate, Django, C#/.NET
- Systems & Reliability: Multithreading, performance tuning, event-driven / async systems, MQ-like messaging, production debugging, log analysis, on-call incident response, RCA
- Data & Observability: Oracle, PL/SQL, PostgreSQL, relational databases, AWS, Grafana, Prometheus, numpy, pandas, Plotly, parallel data processing
- AI & Agentic: AI agents, LLMs, prompt engineering, coding agents (Codex, Claude Code, Antigravity CLI, OpenCode), machine learning, computer vision, empirical evaluation
- Engineering Practices: Test-driven development, JUnit, Mockito, code reviews, technical leadership, Agile, Unix, Docker, CI/CD
- Client Delivery: Requirements gathering, stakeholder engagement, cross-team collaboration, production deployments, incident communication

## Experience

### Senior Software Development Engineer — ION Trading

Noida, India | Aug 2020–Present

- Designed and delivered XTP, ION's real-time back-office trading product, in production for major global trading firms and banks.
- Led a Java multithreading refactor that increased trade-processing throughput by 20x during end-of-day batch runs — scoped requirements with traders, delivered with zero production incidents.
- Won IONathon XTP 1.0 for developing an off-heap persistent cache that eliminates inter-process calls, boosting XTP's performance by up to 50x in supported workflows.
- Developed Alazium, an automated log-analysis tool (Python + regex, parsing 100 GB+ of production logs), reducing incident triage time by 30% for the engineering team.
- Designed and deployed an automatic recovery feature for halted end-of-day processing, cutting downtime by 90% and eliminating after-hours operator calls.
- Built a caching layer for CI builds that predownloads artifacts in parallel, cutting build times by up to 40% and AWS monthly costs by 35%.
- Built features on XTP's in-house event-driven messaging system (MQ-like, Kafka-like), handling async workflows and failure recovery at scale.
- Provided technical leadership for cross-team migration of CI infrastructure from Red Hat 7 to Red Hat 8 — coordinated cutover windows, ran design and code reviews, documented migration paths, zero downtime.
- Redesigned historical-data cleanup with a linear-regression approach, improving database performance by 95% under peak load.
- Provided daily production support for large-scale Oracle databases — fine-tuning queries and SQL plans, benchmarking slow queries, and debugging AWR reports.
- Built on-demand C#/.NET pagination for the XTP GUI over millions of contracts — replaced multi-minute full loads and eliminated client crashes in affected workflows.
- Designed and implemented concurrent price fetchers over Kalshi and Polymarket REST APIs, persisting millions of prices in under 5 minutes.

### Software Development Intern — Holisol Logistics

Delhi, India | Jun 2019–Sep 2019

- Built a Daily Run Sheet Generator with a Django frontend to optimize logistics deliveries — end-to-end from requirements to deployment.
- Presented directly to the company founder and secured production deployment approval, shipping to live daily operational use as an intern.

## Projects

### [TailCache](https://github.com/Enixes/TailCache)

- Reproducible Java 21 benchmarking harness comparing on-heap (Caffeine) vs off-heap (Chronicle Map) caching under deterministic synthetic workloads — 100k-key traces over 2,048 resident entries, pre-generated so no RNG or allocation pollutes the measured path.
- Measures full latency distributions (p50/p95/p99/p99.9) via JMH (5 warmup + 5 measurement iterations, 3 fresh forks) — tail behaviour, GC pressure, and off-heap value-materialization costs, not headline throughput.
- Pinned toolchain (Gradle Kotlin DSL, JMH 1.37, JUnit determinism tests); research in progress.

### Agentic Personal Assistant

- Built a personal AI assistant using free NVIDIA models and AI coding agents (Codex, Claude Code, Antigravity CLI, OpenCode) — prototype to deployed 24/7 system accessible from a phone via messenger apps.
- Designed for async message handling, persistent state, and fault-tolerant 24/7 operation on constrained free-tier hardware.
- Containerised (Docker) for portable deployment; includes Prometheus metrics endpoint and Grafana dashboard for monitoring response latency, uptime, and error rates.
- Sustained 24/7 operation with <2s median response latency across 100+ conversation sessions and zero data loss over a 30-day continuous run.

### [Hybrid Social Group Algorithm](https://link.springer.com/article/10.1007/s12559-021-09848-3)

- Developed a meta-heuristic algorithm to overcome local minima and maxima in machine-learning processes.
- Applied the algorithm to COVID-19 detection from chest X-ray images, achieving 99.31% accuracy.
- Published the work in *Cognitive Computation*, where it has been cited by 80+ papers.

### Wardrobe AI

- Built a personal wardrobe assistant that lets users scan existing photos to automatically create a digital wardrobe.
- Enables users to try on clothes virtually and make better-informed purchasing decisions.

### Lung Disease Prediction

- Developed an automated application to detect and predict the onset of lung diseases from X-ray images.
- Achieved over 99% accuracy using a meta-heuristic algorithm.

## Publications

### COVID-19 Infection Detection from Chest X-Ray Images

Springer | Mar 2021

- Developed the Hybrid Social Group Optimization algorithm for COVID-19 detection from chest X-ray images with over 99% accuracy.
- Published in the *Cognitive Computation* journal.

## Education

### Bachelor of Technology — Computer Science and Engineering

Maharaja Agrasen Institute of Technology, Delhi | Aug 2016–Jul 2020 | CGPA: 8.3

## Recognition

- Top 0.1% performer at ION Trading.
- Won IONathon XTP 1.0 hackathon at ION Trading.
- Inspire program fellow: Awarded for outstanding academics in Xth standard
- 99.9 percentile in JEE Advanced
