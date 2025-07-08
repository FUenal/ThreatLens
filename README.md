# MORE COMING SOON!

# ⚡ ThreatLens: A Modern, AI-Powered Platform for Vulnerability Intelligence and Asset Risk Prioritization

> Building a scalable, real-time vulnerability management solution is hard. But with the right combination of open-source tools, LLMs, and domain expertise, it’s possible—and worth it.

---

![](<./images/showcase_high.gif>)

## The Vulnerability Overload Crisis

Every day, dozens of new CVEs (Common Vulnerabilities and Exposures) are published. Security teams are expected to process them, evaluate their risk, and take action—all before the next wave arrives. Some vulnerabilities are critical and need immediate patching. Many are not. But in the moment, it’s not always clear which is which.

Most organizations still struggle to answer one fundamental question: **Which vulnerabilities actually matter to us?**

Traditional vulnerability management tools help detect weaknesses, but they rarely offer prioritization tailored to your environment. Alerts are fired off indiscriminately. Time is wasted investigating irrelevant issues. And often, the vulnerabilities that pose real risk get lost in the noise.

The consequences of missing a single critical CVE affecting a key system can be devastating. I saw this gap firsthand—and set out to close it.

---

## Why I am Building ThreatLens

Working as a cybersecurity analyst, I observed how hard it was for our team to confidently assess the flood of new vulnerabilities. We had scanners and feeds. But we lacked the one thing we truly needed: **context**.

We didn’t always know which CVEs affected which systems, or how urgent a fix really was. Risk assessments were largely based on CVSS scores alone—ignoring asset value, business impact, and real-world exploitability.

So I decided to build **ThreatLens**, a modern vulnerability intelligence platform that merges real asset data with real-time threat analysis and AI-based prioritization. The goal: help our team act faster, more intelligently, and with more confidence.

---

## 🚀 What Is ThreatLens?

ThreatLens is an end-to-end platform for managing CVEs at scale in a way that actually aligns with organizational risk.

At its core, the platform ingests vulnerability data from authoritative sources like the National Vulnerability Database (NVD), EPSS (Exploit Prediction Scoring System), CISA’s Known Exploited Vulnerabilities (KEV) catalog, and Microsoft Patch Tuesday updates. It then **enriches this data with AI**, **matches it against our real-world infrastructure**, and produces **clear, actionable insights** for remediation.

ThreatLens integrates directly with our internal asset inventory—mapping CVEs to affected systems based on OS, installed software, CPEs, and more. It uses LLMs (Large Language Models) to analyze vulnerability descriptions, estimate severity, and generate human-readable summaries. And it delivers the output through a clean Streamlit-based dashboard, weekly executive reports, and automated remediation workflows.

It doesn’t just tell you what’s vulnerable. It tells you what’s at risk—and what to do next.

---

## Before ThreatLens: A Manual and Inefficient Process

Prior to ThreatLens, managing vulnerabilities was an arduous and reactive task. Security analysts had to sift through long lists of CVEs manually, cross-reference assets with vague software tags, and rely on static metrics like CVSS to guess severity.

There was no clear mapping between vulnerabilities and our infrastructure. We didn’t have a centralized view of risk across departments. And remediation was often delayed, not because people didn’t care—but because they didn’t have the right data, at the right time, in the right format.

We were spending too much time analyzing and not enough time fixing.

---

## ⚙️ Inside the Architecture of ThreatLens

Designing ThreatLens meant starting from the ground up with modularity, performance, and clarity in mind.

**📷 \[ThreatLens Architecture Diagram]**

The system is divided into key components:

* **ETL Pipelines**: These automatically fetch and normalize vulnerability feeds from multiple sources on a daily basis.
* **Asset Mapper**: This correlates each CVE with known systems inside the organization based on hostnames, operating systems, and Common Platform Enumerations (CPEs).
* **LLM Risk Engine**: Powered by self-hosted LLaMA 3.3 and Gemma 3 models, this module analyzes each CVE for contextual impact, summarizes the threat, and recommends a risk score.
* **Risk Weighting Layer**: Critical systems—what we call "crown jewels"—receive additional risk weighting. This ensures that even medium-severity CVEs affecting high-value assets are surfaced urgently.
* **Dashboard + Reports**: Users interact with the data through a real-time Streamlit dashboard and receive weekly threat reports via email or PDF.
* **Remediation Output Engine**: CVEs that surpass risk thresholds trigger alerts and generate structured ticket data that can be sent to Teams, Slack, or ServiceNow.

Each module can be configured independently and extended as needed. The system is designed to evolve as the threat landscape changes.

---

## 🧠 Using LLMs for Smart CVE Triage

One of the most powerful features of ThreatLens is its AI-based prioritization engine. Instead of manually reading every CVE and trying to assess urgency, we now let large language models take the first pass.

Our models—**LLaMA 3.3 70B** and **Gemma 3 27B**—run locally for performance and privacy. They process each vulnerability and answer key questions:

* How likely is this CVE to be exploited?
* What type of impact could it have (e.g., RCE, DoS, privilege escalation)?
* Which types of systems are affected?
* What is the appropriate response priority?

The output is both a risk classification (e.g., high, medium, low) and a natural language summary that helps our analysts understand the threat at a glance.

This layer has been a game changer. It saves time, improves consistency, and brings human-readable intelligence to the forefront.

---

## 🔗 CVE–Asset Correlation: Context Is Everything

Another major innovation in ThreatLens is its ability to connect vulnerabilities directly to the assets they impact.

Using internal data—including hostname, OS, installed applications, and asset ownership—we map each CVE to the affected systems. We then cross-reference this with business unit tags and a crown jewel classification, which reflects the asset’s criticality to operations.

For example, a medium-severity CVE affecting a test server may not require urgent action. But the same CVE on an Active Directory controller? That’s a different story. ThreatLens makes sure this difference is clear—and reflected in the prioritization.

**📷 \[Table mockup – Asset Name → CVE ID → Risk Score → Owner]**

---

## 🛠️ From Risk to Response

To speed up action, ThreatLens supports:

* Instant alerts to asset owners via Slack or Microsoft Teams
* Remediation tickets exported in JSON or CSV
* Structured integration with ServiceNow or JIRA
* Weekly PDF and HTML summary reports for IT and executives

By automatically closing the loop from detection to response, the platform reduces remediation delays and avoids alert fatigue.

---

## 📊 Dashboards That Make Risk Visible

We built the dashboard in **Streamlit** to help teams at all levels get the visibility they need.

**📷 \[Dashboard mockup with CVE Explorer, charts, filters, trend line]**

You can:

* Filter CVEs by severity, exploitability, crown jewel tag, or business unit
* Track risk exposure over time
* Drill down into specific assets or vulnerability clusters
* Export data views for offline analysis or meetings

Security analysts, patching teams, and leadership all get value from the same system.

---

## 🧩 Challenges I Face

**🧱 Data Integrity**
Public CVE feeds are inconsistent. I have to build schema validators and enrichment functions to ensure each CVE had the metadata we needed.

**🔀 Asset Mapping**
CPE strings and product names aren’t standardized. Matching these to real-world software inventory is harder than expected.

**🔁 Alert Fatigue**
Too many alerts can backfire. We will introduce risk thresholds, filtering logic, and manual overrides to keep things focused and useful.

**⚖️ Explainability in AI**
LLMs aren’t perfect. Every decision they make—risk rating, summaries—is logged and reviewable. This builds trust and accountability.

---

## 🧑‍💻 My Role and Impact

This project lets me apply my data science and engineering background to solve a mission-critical security problem.

I am designing the architecture, building the pipelines, training the models, and collaborating with our colleagues to refine the workflows. ThreatLens will go from concept to prototype to MVP within 2025, and early testing will begin 2026.

---

## 🧭 What’s Next for ThreatLens

We’re actively developing new features, including:

* ExploitDB and Metasploit integration
* IOC ingestion and MISP correlation
* Real-time threat detection fusion
* SLA dashboards and patch tracking analytics
* Potential open-sourcing (depending on deployment outcomes)

---

