<div align="center">

# GokturkFK

**Siber Güvenlik Mühendisliği · Açık Kaynak Savunma Platformları · Kurumsal Yazılım**

<br/>

[![GitHub Org](https://img.shields.io/badge/GitHub-GokturkFK-181717?style=flat-square&logo=github)](https://github.com/GokturkFK)
[![Go](https://img.shields.io/badge/Go-1.25-00ADD8?style=flat-square&logo=go&logoColor=white)](https://go.dev/)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Docker](https://img.shields.io/badge/Docker-Air--Gapped%20Ready-2496ED?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Storage-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

*Kurucular: [**Kübra Uzun**](https://github.com/uzunkubra50) & [**Fetih Çakmak**](https://github.com/fetihcakmak)*

**🇹🇷 Türkçe** · [🇬🇧 English](#-english)

</div>

---

## Biz Kimiz

**GokturkFK**, yüksek güvenceli **açık kaynak siber güvenlik platformları** ve **kurumsal yazılım çözümleri** geliştiren bağımsız bir yazılım ve güvenlik mühendisliği ekibidir.

Mühendislik odağımız; ölçülebilir, deterministik ve üretim ortamlarında sürdürülebilir sistemler inşa etmektir. Açık kaynak tarafında aktif savunma, kimlik güvenliği, yapay zekâ çalışma zamanı koruması ve regülasyon uyumluluğu üzerine modüler ürünler geliştiriyor; bunun yanında özel kurumsal projelerde uçtan uca yazılım mühendisliği ve DevSecOps çözümleri üretiyoruz.

---

## Açık Kaynak Siber Güvenlik Ekosistemi

### Birleşik Aldatma ve Kimlik Güvenliği Platformu (Go)

Tek bir dondurulmuş sözleşme ([`gokturk-core`](https://github.com/GokturkFK/gokturk-core)) etrafında kurulmuş, air-gap ortamlara hazır modüler bir güvenlik platformu. Her ürün aynı korelasyon motoruna bağlanır ve **tasarımı gereği sıfır yanlış pozitif** üreten ortak bir SOC alarm akışını besler.

| Repo | Katman | Teknoloji | Özet |
| :--- | :---: | :--- | :--- |
| [**`gokturk-core`**](https://github.com/GokturkFK/gokturk-core) | Ortak Çekirdek | Go 1.25 | Dondurulmuş `trap` sözleşmesi (`Provider`, `Decoder`, `TripEvent`) ve belirlenimci, sıfır-FP `correlate` motoru (`High` → `Critical` kampanya birleştirme). |
| [**`gokturk-deception-mesh`**](https://github.com/GokturkFK/gokturk-deception-mesh) | Platform P1 | Go · NATS JetStream · PostgreSQL · Streamlit | Air-gap kimlik kanaryası platformu. Çalınan servis hesabı kullanımını ≤5 saniyede tespit eder; SIEM (CEF), Telegram ve webhook'lara dağıtır. |
| [**`gokkalkan`**](https://github.com/GokturkFK/gokkalkan) | Platform P2 | Go · PostgreSQL · MITRE ATLAS | Ajan tabanlı yapay zekâ çalışma zamanı güvenliği: varsayılan-reddet MCP egress proxy, ajan honeypot araçları, tool-poisoning tespiti ve imzalı işlem makbuzları. |
| [**`gokzincir`**](https://github.com/GokturkFK/gokzincir) | Platform P3 | Go · PostgreSQL · MITRE ATT&CK | İnsan-olmayan kimlik (NHI) envanteri, blast-radius grafik analizi ve fark edilmeyen sahte NHI ekimiyle sıfır-FP yanal hareket tespiti. |

### Uzmanlaşmış Güvenlik Araştırma ve Uyumluluk Araçları (Python)

| Repo | Alan | Teknoloji | Özet |
| :--- | :--- | :--- | :--- |
| [**`gokturk-av`**](https://github.com/GokturkFK/gokturk-av) | Otomotiv Siber Güvenliği | Python · Streamlit · SQLite · SocketCAN | Otonom shuttle'lar için uçtan uca güvenlik testi ve uyumluluk platformu. **55/69 UN R155 Annex 5** vektörü (yazılımla erişilebilenlerin %100'ü), **29 test modülü**, otomatik **ISO/SAE 21434 TARA** ve `.docx` denetim raporları. |
| [**`gokturk-honeypot-soc`**](https://github.com/GokturkFK/gokturk-honeypot-soc) | Aktif Savunma ve SOC | Python · Streamlit · IsolationForest · SQLite | Çok servisli honeypot (SSH, FTP, MySQL, Web); hibrit ML davranış analizi, MITRE ATT&CK eşleme, APT korelasyonu, Canary honeydoc'lar ve otomatik PDF/Telegram raporlama. |
| [**`gokturk-bypass`**](https://github.com/GokturkFK/gokturk-bypass) | Saldırı Keşfi | Python · FastAPI · React · SQLite | İzin-öncelikli, fail-closed WAF/CDN araştırma platformu; pasif Origin Mapper (crt.sh, favicon hash, VHost diff) sonuçlarını doğrudan aktif BypassBench kanıt üretimine bağlar. |

---

## Mühendislik İlkelerimiz

- **Tasarımı Gereği Sıfır Yanlış Pozitif:** Aldatma platformlarımızda alarmlar gürültülü anomali eşiklerinden değil, yalnızca kesin kanarya/tuzak eşleşmelerinden doğar.
- **Air-Gap ve Self-Hosted Önceliği:** Kurumsal ve izole ağlarda harici bağımlılık olmadan çalışabilen Docker yığınları ve tekrarlanabilir kurulum süreçleri.
- **Dondurulmuş Sözleşmeler ve Temiz Mimari:** Servisler arası açık wire contract'lar, modüler yapı ve her kritik teknik kararın belgelenmesi.
- **Sürekli Güvenlik Doğrulaması:** Otomatik CI testleri, konteyner zafiyet taraması (Trivy) ve sorumlu zafiyet bildirimi ([`SECURITY.md`](../SECURITY.md)).

---

## Teknoloji Yığını (Açık Kaynak)

| Alan | Teknolojiler |
| :--- | :--- |
| **Güvenlik ve Backend** | Go 1.25, Python 3.10+, FastAPI, NATS JetStream, PostgreSQL, SQLite |
| **Arayüz ve Görselleştirme** | Streamlit, React |
| **Altyapı ve Kalite** | Docker ve Compose, GitHub Actions CI, Trivy, `golangci-lint`, Pytest, Ruff |
| **Standartlar ve Çerçeveler** | MITRE ATT&CK, MITRE ATLAS, OWASP Agentic Top 10, UN R155 Annex 5, ISO/SAE 21434 (TARA) |

---

<a id="-english"></a>

<details>
<summary><b>🇬🇧 English</b> — click to expand</summary>

<br/>

## Who We Are

**GokturkFK** is an independent software and cybersecurity engineering team building **high-assurance open-source security platforms** and **enterprise software solutions**.

Our engineering philosophy centers on deterministic, verifiable, and production-ready systems. In open source, we focus on active defense, non-human identity governance, agentic AI runtime security, and regulatory compliance testing—alongside end-to-end software engineering and DevSecOps work in enterprise domains.

## Open-Source Cybersecurity Ecosystem

A modular, air-gap-ready security platform built around a single frozen wire contract ([`gokturk-core`](https://github.com/GokturkFK/gokturk-core)). Every product plugs into the same correlation engine and feeds a unified SOC alert stream with **zero false positives by construction**.

| Repository | Layer / Domain | Stack | Summary |
| :--- | :---: | :--- | :--- |
| [**`gokturk-core`**](https://github.com/GokturkFK/gokturk-core) | Shared Kernel | Go 1.25 | Frozen `trap` wire contract and deterministic zero-FP `correlate` engine (`High` → `Critical` campaign merging). |
| [**`gokturk-deception-mesh`**](https://github.com/GokturkFK/gokturk-deception-mesh) | Platform P1 | Go · NATS JetStream · PostgreSQL · Streamlit | Air-gapped credential canary platform; detects stolen service-account usage in ≤5 s and fans out to SIEM (CEF), Telegram, and webhooks. |
| [**`gokkalkan`**](https://github.com/GokturkFK/gokkalkan) | Platform P2 | Go · PostgreSQL · MITRE ATLAS | Agentic AI runtime security: deny-by-default MCP egress proxy, agent honeypot tools, tool-poisoning detection, signed action receipts. |
| [**`gokzincir`**](https://github.com/GokturkFK/gokzincir) | Platform P3 | Go · PostgreSQL · MITRE ATT&CK | NHI inventory, blast-radius graph analysis, and stealth decoy NHI seeding with zero-FP lateral movement detection. |
| [**`gokturk-av`**](https://github.com/GokturkFK/gokturk-av) | Automotive | Python · Streamlit · SocketCAN | **55/69 UN R155 Annex 5** vectors, **29 test modules**, automated **ISO/SAE 21434 TARA** and `.docx` audit reports. |
| [**`gokturk-honeypot-soc`**](https://github.com/GokturkFK/gokturk-honeypot-soc) | Active Defense | Python · Streamlit · IsolationForest | Multi-service honeypot with hybrid ML behavioral analysis, MITRE ATT&CK mapping, APT correlation, and automated reporting. |
| [**`gokturk-bypass`**](https://github.com/GokturkFK/gokturk-bypass) | Offensive Recon | Python · FastAPI · React | Permission-first, fail-closed WAF/CDN research chaining passive origin discovery into active bypass proof generation. |

## Engineering Principles

- **Zero false positives by construction** — alerts stem strictly from deterministic canary/decoy matches.
- **Air-gap & self-hosted first** — reproducible Docker stacks that run cleanly in isolated environments.
- **Frozen contracts & clean architecture** — versioned wire contracts and modular boundaries across services.
- **Continuous verification** — automated CI test suites, Trivy container scanning, and responsible disclosure ([`SECURITY.md`](../SECURITY.md)).

</details>

---

<div align="center">
  <sub><a href="https://github.com/uzunkubra50">@uzunkubra50</a> & <a href="https://github.com/fetihcakmak">@fetihcakmak</a> tarafından geliştirilmektedir · <a href="https://github.com/GokturkFK">GokturkFK</a></sub>
</div>
