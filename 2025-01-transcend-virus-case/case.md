# Case Report – Transcend StoreJet 1TB (Logical Damage – Malware Hidden-Data Case)

# 🧾 DATA RECOVERY CASE RECORD
(Internal documentation — not client-facing)

# Case ID
2024-01

---

## 🧩 Media
**Model:** Transcend StoreJet  
**Capacity:** 1TB  
**Interface:** USB 3.0  
**Serial (first 4 chars only):** Not exposed — S/N not available through enclosure  

---

## 🧭 Case Type
- Logical damage (malware-induced hidden folders)

---

## 🩺 Symptoms Observed
• Drive mounts normally in Windows  
• All main folders appear empty (Pictures, Movies, Projects)  
• Explorer displays decoy empty folders  
• User believed "everything is gone"  
• File tree count (Properties) suggested real size still used  

---

## 🧬 Failure Signature (What actually broke)
Malware altered directory attributes and replaced visible folders with empty fake clones.  
Original data remained intact — no filesystem or physical damage.

---

## 🛠 Acquisition / Imaging
**Not applicable — logical-only / no physical risk**  
Reason: SMART normal, drive healthy, no slow reads.  
→ Live-disk work was safe & chosen to minimize turnaround time.

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

*(Recovered client data is **never** stored.)*

---

## 🧰 Recovery Actions
• Confirmed logical-only failure  
• Malware scan performed before touching attributes  
• `attrib -h -s /s /d` unsuccessful (attributes hardened)  
• DMDE used to enumerate NTFS & reveal original hidden folders  
• Manual 1:1 hierarchy reconstruction (directory-by-directory)  
• Temporary staging performed on analyst's dedicated offline SSD (wiped after hand-off)  
• Drive formatted → data copied back → verification performed

---

## 📦 Output / Result
**Percent recovered:** 100%  
**Hierarchy preserved:** yes — full original tree reconstructed 1:1 manually  
**Carving required:** no  
**Client goals met:** yes — full recovery + healthy usable disk

---

## ⏱ Time Breakdown
| Stage | Duration |
|--------|----------|
| Imaging (ddrescue) | N/A |
| Malware scan / safety checks | ~1 hour |
| Manual extraction & rebuild | ~10–12 hours |
| Format + copy-back + verification | ~1–2 hours |

**Total Analyst Time (active):** ~12–14 hours  
**Calendar Duration:** ~4–5 days (intermittent availability)

---

## 🔒 Privacy Notes
• No file previews or client names retained  
• Temporary staging disk wiped after delivery  
• Consent verbally received for anonymized record

---

## 🧭 Reflection / Lessons
• Malware often mimics catastrophic data loss — always rule it out first  
• Manual rebuild via DMDE Free costs time — invest in licensed tool  
• Temporary staging = liability → must maintain dedicated recovery disk

---

## ✔ Next Time I Will
Document a written wipe-policy and log wipe events instead of relying on memory.
