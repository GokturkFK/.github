<div align="center">

# GokturkFK

**Kurumsal SaaS Sistemleri · Siber Güvenlik Mühendisliği · Belirlenimci Yazılım**

<br/>

[![GitHub Org](https://img.shields.io/badge/GitHub-GokturkFK-181717?style=flat-square&logo=github)](https://github.com/GokturkFK)
[![TypeScript](https://img.shields.io/badge/TypeScript-Next.js%20%7C%20NestJS%20%7C%20Expo-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Go](https://img.shields.io/badge/Go-1.25-00ADD8?style=flat-square&logo=go&logoColor=white)](https://go.dev/)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Flutter](https://img.shields.io/badge/Flutter-Cross--Platform-02569B?style=flat-square&logo=flutter&logoColor=white)](https://flutter.dev/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-RLS%20%7C%20Event--Sourced-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

*Kurucular: [**Kübra Uzun**](https://github.com/uzunkubra50) & [**Fetih Çakmak**](https://github.com/fetihcakmak)*

**🇹🇷 Türkçe** · [🇬🇧 English](#-english)

</div>

---

## Biz Kimiz

**GokturkFK**, **üretim seviyesinde çok kiracılı kurumsal SaaS ürünleri** ve **yüksek güvenceli siber güvenlik platformları** geliştiren bağımsız bir yazılım mühendisliği ekibidir.

Birbirini tamamlayan iki mühendislik hattında çalışıyoruz:
1. **Kurumsal SaaS ve Ürün Mühendisliği:** Çok kiracılı web ve mobil platformlar, mevzuat uyumluluk sistemleri, çevrimdışı öncelikli saha uygulamaları ve belirlenimci simülasyon motorları — veritabanı seviyesinde güvenlik ve denetlenebilirlikle.
2. **Göktürk Siber Güvenlik Ekosistemi (Açık Kaynak):** Sıfır yanlış pozitifli aldatma (deception) platformları, ajan tabanlı yapay zekâ çalışma zamanı güvenliği, insan-olmayan kimlik (NHI) yönetişimi, otonom araç uyumluluk testleri (UN R155 / ISO 21434) ve saldırı/savunma araştırma araçları.

---

## 1. Kurumsal SaaS ve Ürün Mühendisliği *(Özel Repolar)*

Gerçek operasyonel gereksinimler, mevzuat uyumluluğu ve yüksek güvenlik standartlarıyla tasarladığımız ticari ve ürün odaklı sistemler:

| Ürün | Alan | Mimari ve Teknoloji | Öne Çıkanlar |
| :--- | :--- | :--- | :--- |
| **İSG Platform** | İş Sağlığı ve Güvenliği (6331 sayılı Kanun) | Monorepo · Next.js 16 · Expo 57 (React Native) · PostgreSQL 16 (171 migration) · Kysely · MinIO · Self-hosted Ollama | Veritabanında zorlanan çok kiracılı RLS (`withUser`), trigger tabanlı append-only denetim kaydı, `tus` ile devam ettirilebilir yükleme, Playwright PDF, çevrimdışı mobil SQLite ve KVKK uyumlu yerel yapay zekâ asistanı. |
| **Dershane ve Öğrenci Koçluğu SaaS** | Çok Kiracılı Eğitim Teknolojisi | Monorepo · NestJS 12 · Next.js 16 · Flutter · PostgreSQL · Redis · WebSocket | **38+ backend domain modülü** (koçluk, deneme analizi, ödev, yoklama, QR, rehberlik, takvim, mesajlaşma, finans), **42 ekranlık tasarım sistemi**, 2FA çift onaylı IBAN/sözleşme güvenliği ve KVKK anonimleştirme. |
| **Ötüken** | Tarihî Strateji Simülasyonu | Monorepo · Saf TypeScript (`sim-core`) · React · Vite · SVG · Capacitor 8 | Oyun motoru kullanmayan mimari, tohumlu RNG ile belirlenimci saatlik simülasyon (4 mevsim × 30 gün), headless CSV simülasyon koşucusu, Zod ile doğrulanan JSON içerik ve 33 ekranlık özgün görsel tasarım. |
| **Gokturk Web** | Ekip ve Ürün Vitrini | Next.js 16 · React 19 · Tailwind CSS v4 · MDX · `next-intl` (TR/EN) · Resend | Build anında prosedürel görsel üretimi (ebru, parşömen dokusu, deri kapak, dinamik OG görselleri) içeren iki dilli web sitesi. |
| **Agri-ERP** *(Geliştirme Aşamasında)* | Çevrimdışı Öncelikli Karma Çiftlik ERP Prototipi | Flutter · Python · PostgreSQL (RLS, 24 migration) | Bitemporal, append-only olay kaydı (`ops.events`), istemcide üretilen UUID v7, sunucuda yerel birim → SI dönüşümü ve zorunlu RLS izolasyon testleri. |

---

## 2. Göktürk Siber Güvenlik Ekosistemi *(Açık Kaynak)*

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

- **Güvenlik Veri Katmanında Zorlanır:** PostgreSQL Row-Level Security ile çok kiracılı izolasyon, en az yetkili çalışma rolleri, CI'da negatif RLS testleri ve trigger tabanlı append-only denetim kayıtları — yalnızca uygulama koduna güvenilmez.
- **Tasarımı Gereği Sıfır Yanlış Pozitif:** Aldatma platformlarımızda alarmlar gürültülü anomali eşiklerinden değil, yalnızca kesin kanarya/tuzak eşleşmelerinden doğar.
- **Veri Egemenliği ve Mahremiyet Önceliği:** Self-hosted kuruluma uygun dağıtımlar, air-gap Docker Compose yığınları ve mevzuatın (KVKK / GDPR) veri çıkışını yasakladığı yerlerde yerel yapay zekâ çıkarımı (Ollama).
- **Belirlenimci Çekirdekler ve Saf Sözleşmeler:** İş/simülasyon çekirdekleri arayüzden ve I/O'dan yalıtılır, servisler arası sözleşmeler dondurulur ve her kritik karar Mimari Karar Kayıtları (ADR) ile belgelenir.

---

## Teknoloji Yığını

| Alan | Teknolojiler |
| :--- | :--- |
| **Backend ve Güvenlik** | TypeScript, NestJS 12, Go 1.25, Python 3.10+, FastAPI, PostgreSQL 16 (RLS, PL/pgSQL), Redis, NATS JetStream, SQLite |
| **Frontend ve Mobil** | Next.js 16, React 19, Tailwind CSS v4, Flutter / Dart, React Native / Expo 57, Capacitor 8, Streamlit |
| **Altyapı ve Kalite** | Docker ve Compose, MinIO (S3), Playwright, Vitest, Pytest, `golangci-lint`, GitHub Actions CI, Trivy, `gitleaks` |
| **Standartlar ve Çerçeveler** | 6331 sayılı İSG Kanunu, KVKK, MITRE ATT&CK, MITRE ATLAS, OWASP Agentic Top 10, UN R155 Annex 5, ISO/SAE 21434 (TARA) |

---

<a id="-english"></a>

<details>
<summary><b>🇬🇧 English</b> — click to expand</summary>

<br/>

## Who We Are

**GokturkFK** is an independent software & cybersecurity engineering studio building **production-grade multi-tenant enterprise SaaS products** and **high-assurance security platforms**, across two complementary tracks:

1. **Enterprise SaaS & Product Engineering (Private Systems):** Multi-tenant web/mobile platforms, regulatory compliance systems, offline-first field apps, and deterministic simulation engines built with database-level security and auditability.
2. **Göktürk Security Ecosystem (Open Source):** Zero-false-positive deception platforms, agentic AI runtime security, non-human identity (NHI) governance, autonomous vehicle compliance testing (UN R155 / ISO 21434), and offensive/defensive research tooling.

## 1. Enterprise SaaS & Product Engineering *(Private Showcase)*

| Product | Domain | Highlights |
| :--- | :--- | :--- |
| **İSG Platform** | Occupational Health & Safety (Law No. 6331) | Next.js 16 + Expo 57 monorepo, PostgreSQL 16 RLS (171 migrations), append-only audit, offline mobile, KVKK-compliant self-hosted AI (Ollama). |
| **Dershane & Student Coaching SaaS** | Multi-tenant EdTech | NestJS 12 + Next.js 16 + Flutter, 38+ domain modules, 42-screen design system, 2FA dual-approval payment governance. |
| **Ötüken** | Historical strategy simulation | Engine-free React/SVG/Capacitor 8 client over a pure, deterministic seeded-RNG TypeScript simulation core. |
| **Gokturk Web** | Studio showcase | Bilingual Next.js 16 site with procedural build-time asset pipelines (ebru marbling, parchment, OG images). |
| **Agri-ERP** *(Work in Progress)* | Offline-first farm ERP prototype | Bitemporal append-only event sourcing, client UUID v7, mandatory RLS, and server-side local-unit → SI conversion. |

## 2. Göktürk Security Ecosystem *(Open Source)*

A modular, air-gap-ready security platform built around a single frozen wire contract ([`gokturk-core`](https://github.com/GokturkFK/gokturk-core)). Every product plugs into the same correlation engine and feeds a unified SOC alert feed with **zero false positives by construction**.

| Repository | Layer | Stack | Summary |
| :--- | :---: | :--- | :--- |
| [**`gokturk-core`**](https://github.com/GokturkFK/gokturk-core) | Shared Kernel | Go 1.25 | Frozen `trap` wire contract and deterministic zero-FP `correlate` engine (`High` → `Critical` campaign merging). |
| [**`gokturk-deception-mesh`**](https://github.com/GokturkFK/gokturk-deception-mesh) | Platform P1 | Go · NATS JetStream · PostgreSQL · Streamlit | Air-gapped credential canary platform; detects stolen service-account usage in ≤5 s and fans out to SIEM (CEF), Telegram, and webhooks. |
| [**`gokkalkan`**](https://github.com/GokturkFK/gokkalkan) | Platform P2 | Go · PostgreSQL · MITRE ATLAS | Agentic AI runtime security: deny-by-default MCP egress proxy, agent honeypot tools, tool-poisoning detection, signed action receipts. |
| [**`gokzincir`**](https://github.com/GokturkFK/gokzincir) | Platform P3 | Go · PostgreSQL · MITRE ATT&CK | NHI inventory, blast-radius graph analysis, and stealth decoy NHI seeding with zero-FP lateral movement detection. |
| [**`gokturk-av`**](https://github.com/GokturkFK/gokturk-av) | Automotive | Python · Streamlit · SocketCAN | **55/69 UN R155 Annex 5** vectors, **29 test modules**, automated **ISO/SAE 21434 TARA** and `.docx` audit reports. |
| [**`gokturk-honeypot-soc`**](https://github.com/GokturkFK/gokturk-honeypot-soc) | Active Defense | Python · Streamlit · IsolationForest | Multi-service honeypot with hybrid ML behavioral analysis, MITRE ATT&CK mapping, APT correlation, and automated reporting. |
| [**`gokturk-bypass`**](https://github.com/GokturkFK/gokturk-bypass) | Offensive Recon | Python · FastAPI · React | Permission-first, fail-closed WAF/CDN research chaining passive origin discovery into active bypass proof generation. |

## Engineering Principles

- **Security enforced at the data layer** — PostgreSQL RLS, least-privilege roles, negative RLS tests in CI, trigger-driven audit trails.
- **Zero false positives by construction** — alerts only from deterministic canary/decoy matches.
- **Data sovereignty** — self-hosted, air-gapped stacks and local AI inference where KVKK / GDPR require it.
- **Deterministic cores & frozen contracts** — isolated domain cores, versioned wire contracts, ADR-documented trade-offs.

</details>

---

<div align="center">
  <sub><a href="https://github.com/uzunkubra50">@uzunkubra50</a> & <a href="https://github.com/fetihcakmak">@fetihcakmak</a> tarafından geliştirilmektedir · <a href="https://github.com/GokturkFK">GokturkFK</a></sub>
</div>
