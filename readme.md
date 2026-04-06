<h1 align="center">Mini-SOC-Lab: Cyber Kill Chain & Detection Engineering 🛡️⚔️</h1>

<p align="center">
	<strong>Progetto per il corso di Network Security</strong><br />
	Università degli Studi di Napoli Federico II<br />
	Prof. Simon Pietro Romano
</p>

<p align="center">
	<a href="./Doc_RH_mini_soc_lab.pdf"><img alt="Documentazione" src="https://img.shields.io/badge/Documentazione-PDF-0A66C2?style=for-the-badge"></a>
	<a href="./PoC_Attack.mp4"><img alt="Proof of Concept" src="https://img.shields.io/badge/PoC-Video-C62828?style=for-the-badge"></a>
</p>

---

## Indice

- [Abstract](#abstract)
- [Tecnologie e Strumenti Principali](#tecnologie-e-strumenti-principali)
- [Documentazione Ufficiale](#documentazione-ufficiale)
- [Proof of Concept (PoC)](#proof-of-concept-poc)
- [Autori](#autori)

---

## Abstract

> Questo progetto illustra la progettazione, l'esecuzione e l'analisi di una **Cyber Kill Chain** completa all'interno di un ambiente di laboratorio virtualizzato. L'obiettivo principale è dimostrare le dinamiche di un attacco informatico moderno e, parallelamente, testare l'efficacia di un'infrastruttura di monitoraggio e rilevamento avanzata (approccio *Assume Breach* e *Defense-in-Depth*).

Il lavoro è suddiviso in due macro-fasi operative:

- <span style="color:#d32f2f;"><strong>Fase Red Team (Attacco)</strong></span>: Simulazione di un'infiltrazione realistica partendo dalla compromissione di un servizio perimetrale vulnerabile (Webmin tramite Command Injection). L'attacco prosegue con tecniche di *Network Pivoting* e tunneling (Socat) per aggirare la segmentazione di rete, concludendosi con un movimento laterale verso un target Windows interno sfruttando la vulnerabilità **PrintNightmare (CVE-2021-1675)**. L'impiego di tecniche *Living off the Land* (es. `certutil.exe`) ha permesso di stabilire la persistenza e il Command & Control tramite il framework **Caldera**.
- <span style="color:#1565c0;"><strong>Fase Blue Team (Difesa)</strong></span>: Progettazione di un'architettura di Detection Engineering basata sul SIEM **Wazuh**. Per superare i limiti dei log di sistema standard, la telemetria degli endpoint è stata potenziata tramite *Targeted Auditing* utilizzando **Sysmon** (su Windows) e **Auditd** (su Linux). Sono state scritte regole di correlazione personalizzate e mappate fedelmente sulle tattiche del framework **MITRE ATT&CK** per intercettare gli specifici Indicatori di Compromissione (IoC) generati dal Red Team.

---

## Tecnologie e Strumenti Principali

| Categoria | Strumenti |
|---|---|
| **Offensive** | Metasploit, Nmap, Impacket, Socat, MITRE Caldera (C2) |
| **Defensive** | Wazuh (SIEM/XDR), Microsoft Sysmon, Auditd |
| **Frameworks** | MITRE ATT&CK |

---

## Documentazione Ufficiale

Questo README fornisce solo una panoramica ad alto livello del progetto.

Per l'analisi approfondita delle vulnerabilità, la topologia di rete, l'elenco esatto dei payload eseguiti, il codice delle regole di detection e i log intercettati, **si prega di fare riferimento alla documentazione tecnica ufficiale allegata a questa repository:**

<p>
	<strong><a href="./Doc_RH_mini_soc_lab.pdf">Doc_RH_mini_soc_lab.pdf</a></strong>
</p>

---

## Proof of Concept (PoC)

A corredo della documentazione, è disponibile la registrazione video completa dell'esecuzione dell'attacco (dall'infiltrazione iniziale fino all'ottenimento della shell tramite Command & Control):

<p>
	<strong><a href="./PoC_Attack.mp4">Guarda il Video PoC_Attack.mp4</a></strong>
</p>

---

## Autori

- **Francesco Prisco** (Matr. M63001738)
- **Francesco Gaetano Niutta** (Matr. M63001802)