# 🧾 DATA RECOVERY CASE RECORD
(Technical documentation — privacy-safe and suitable for public archive)

# Case ID
YYYY-NN  <!-- increment each case -->

---

## 🧩 Media
**Model:**  
**Capacity:**  
**Interface (USB/SATA/NVMe):**  
**Serial (first 4 chars only):** *(optional – record only if accessible or photographed)*  

---

## 🧭 Case Type
(choose one)
- Physical degradation / slow reads
- Logical damage (malware / deleted / formatted)
- Filesystem corruption
- Partition loss
- Mixed / unknown

---

## 🩺 Symptoms Observed
• Slow reads / freezing / disappears / clicking  
• Mounts but shows empty / decoy folders  
• RAW volume  
• Missing partitions  
• etc.

(Add only bullets that apply)

---

## 🧬 Failure Signature (What actually broke)
(Be specific — 1–2 lines)

Examples:
• bad band at 1.2TB – unreadable sectors  
• metadata collapse – missing MFT  
• fake folders + hidden attributes (virus)  
• overwritten GPT / partition table  
• USB bridge failure  

---

## 🛠 Acquisition / Imaging (skip if not applicable)

**If applicable (physical risk / unstable media):**
- ddrescue map: `ddrescue.log`
- Commands:
```
ddrescue -f -n /dev/sdX image.img map.log
ddrescue -f -r1 /dev/sdX image.img map.log
```

**If not applicable (logical-only / safe live disk):**
- N/A – logical-only case (no imaging performed)

Goal: always image first unless 100% confirmed logical-only and low risk.

---

## 📂 Evidence Collected
(only generic / non-sensitive artifacts should be saved)

| Artifact | Included |
|---------|----------|
| device-info.txt | ✔/✘ |
| smartctl.txt | ✔/✘ |
| hdparm.txt | ✔/✘ |
| lsblk.txt | ✔/✘ |
| fdisk.txt | ✔/✘ |
| cropped screenshots | ✔/✘ |

*(Actual recovered files are **never** stored)*

---

## 🗂 Evidence Summary
All evidence stored under:  
`/cases/YYYY-NN-<case-name>/evidence/`

Example contents:
- DMDE scan screenshots
- Partition maps
- SMART UI screenshot
- ddrescue log file (if applicable)

---

## 🧰 Recovery Actions
• Tools used  
• Order of operations  
• Imaging first? or live-disk work?  
• Carving vs metadata recovery  
(Write in short bullet points)

---

## 📦 Output / Result
**Percent recovered:**  
**Hierarchy preserved:** yes / partial / no  
**Carving required:** yes / no  
**Client goals met:** yes / partial / no  

---

## ⏱ Time Breakdown
| Stage | Duration |
|--------|----------|
| Imaging (ddrescue) | |
| Malware scan / analysis | |
| Manual extraction / recovery | |
| Hierarchy rebuild | |
| Final transfer & packaging | |

**Total Analyst Time (active):**  
**Calendar Duration:**  

---

## 🔒 Privacy Notes
(No client names, folder names, or file previews are stored or shown.)

---

## 🧭 Reflection / Lessons
(short bullet list – what changed in your thinking)

---

## ✔ Next Time I Will
(one sentence improvement commitment)

(End of Case Record – do not attach recovered client content)

