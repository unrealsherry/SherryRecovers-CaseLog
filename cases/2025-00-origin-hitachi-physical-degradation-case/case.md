# Case Report – Hitachi 1TB HDD (Physical Degradation – 0% Health)


# 🧾 DATA RECOVERY CASE RECORD
(Technical documentation — sanitized for public portfolio)

# Case ID
2024-00

---

## 🧩 Media
**Model:** Hitachi HUA722010CLA330  
**Capacity:** 1TB  
**Interface:** SATA (removed from external enclosure)  
**Serial (first 4 chars only):** HZ0J  
**Production Date:** Dec-2010  

---

## 🧭 Case Type
- Physical degradation / slow reads

---

## 🩺 Symptoms Observed
• Windows attempted auto-repair on boot  
• Only 2 visible partitions, 1 corrupted / inaccessible  
• Severe slow reads + freezes  
• SMART showed imminent failure (0% health)  

---

## 🧬 Failure Signature (What actually broke)
Physical HDD wear — unstable read band and reallocated sectors (0% health). 
Logical metadata collapse present on 2 partitions prior to acquisition (tree loss pre-existing).

---

## 🛠 Acquisition / Imaging
**Applicable (unstable physical media – imaging mandatory)**  
- ddrescue mapfile: *present (local – not uploaded)*  
- Commands used:
  ```
  ddrescue -f -n /dev/sdX image.img map.log
  ddrescue -f -r1 /dev/sdX image.img map.log
  ```
Environment: SystemRescueCD live OS  
Imaging required multiple days due to retry cycles + fallback mode.

---

## 📂 Evidence Collected
| Artifact | Included |
|---------|----------|
| device-info.txt | ✘ |
| smartctl.txt | ✘ |
| hdparm.txt | ✘ |
| lsblk.txt | ✘ |
| fdisk.txt | ✘ |
| cropped screenshots (UI-only) | ✔ |

*(Actual recovered client files are **never** stored)*

## 🗂 Evidence Summary
All evidence stored under:  
`/2025-00-origin-hitachi-physical-degradation-case/evidence/`
 SMART 0% health status was observed live but not captured — missing documentation noted.


### Evidence Included
The following **neutral, non-sensitive** artifacts were captured:

- `windows-autorepair-boot.jpeg` — Screenshot showing Windows automatic repair attempt
- `windows-explorer-3partitions.jpeg` — Screenshot showing visible/hidden partitions
- `dmde-01-root-view.jpeg` — DMDE root scan result (corrupted partitions visible)
- `dmde-02-tree-view.jpeg` — DMDE directory tree view
- `sysresccd-01.jpeg` — SystemRescue environment booted
- `sysresccd-02.jpeg` — Imaging environment confirmation  
- `.gitkeep` — placeholder file to retain directory in Git

---

## 🧰 Recovery Actions
• Imaging performed before filesystem access  
• Image loaded into DMDE for metadata-based recovery  
• Signature scan → partial NTFS reconstruction  
• Extraction of remaining readable files  

---

## 📦 Output / Result
**Percent recovered:** Not numerically quantified — full disk image acquired; logical file availability varies by partition state  
**Hierarchy preserved:** partial — one partition intact, two arrived already metadata-collapsed  
**Carving required:** yes — limited to collapsed partitions  
**Client goals met:** partial — target files exist inside image, but structured hierarchy cannot be rebuilt

---

## ⏱ Time Breakdown
| Stage | Duration |
|--------|----------|
| Imaging (ddrescue) | ~4–6 days (intermittent retries) |
| Analysis / DMDE scan | ~2–3 hours |
| Extraction | ~1–2 hours |

**Total Analyst Time (active):** ~4–6 hours  
**Calendar Duration:** ~4–6 days  

---

## 🔒 Privacy Notes
• No names or identifiable content published  
• Only cropped tool screenshots included  
• Raw disk image **not** kept — delivered to client  

---

## 🧭 Reflection / Lessons
• Imaging-first saved remaining data — touching live disk would've worsened damage  
• 0%-health drives require patience; time cost is exponential  
• Should obtain SMART & disk metadata artifacts for all future physical cases

---

## ✔ Next Time I Will
Capture full evidence set (SMART + lsblk + fdisk + device-info) before imaging to improve future case comparability.
