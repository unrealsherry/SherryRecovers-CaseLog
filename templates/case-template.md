# 🧾 DATA RECOVERY CASE RECORD
(Technical documentation — privacy-safe and suitable for public archive)

**Template Version:** 1.1

---

# Case ID
YYYY-NN <!-- Increment each case -->

**Case Documentation Version:** 1.1

---

## 🧩 Media

**Model:**  
**Capacity:**  
**Interface (USB/SATA/NVMe):**  
**Serial (first 4 characters only):** *(Optional — record only if accessible and safe to disclose)*

---

## 🧭 Case Type

*(Select all applicable; identify the primary failure type.)*

- [ ] Physical degradation / slow reads
- [ ] Logical damage (malware / deleted / formatted)
- [ ] Filesystem corruption
- [ ] Partition loss
- [ ] Mixed / unknown

**Primary Classification:**  

---

## 🩺 Symptoms Observed

- Slow reads / freezing / device disappears / clicking
- Mounts but shows empty or inaccessible volumes
- RAW volume
- Missing partitions
- Corrupted partition entries
- Other:

*(Add only observations that actually apply.)*

---

## 🧬 Failure Signature (What actually broke)

*(Be specific — 1–2 lines. Distinguish observed symptoms from confirmed causes.)*

Examples:

- Bad sectors at specific regions — unreadable sectors
- Metadata damage — missing or inaccessible MFT structures
- Fake folders + hidden attributes (malware)
- Corrupted GPT / partition table
- USB bridge failure
- Unknown / undetermined

**Observed Failure Signature:**

---

## 🛠 Acquisition / Imaging

*(Skip if not applicable.)*

**If applicable (physical risk / unstable media):**

**Imaging Tool:**  
**Source Device:**  
**Destination Image:**  
**Mapfile:**  
**Mapfile Backup:**  

**Commands Actually Used:**

```bash
# Record the exact commands used during acquisition.
# These are examples only; do not execute without verifying device paths.

ddrescue -f -n /dev/sdX image.img map.log
ddrescue -f -r1 /dev/sdX image.img map.log
```

**Final Acquisition Statistics:**

| Metric | Result |
|---|---|
| Total source capacity | |
| Rescued | |
| Rescued percentage | |
| Non-tried | |
| Non-trimmed | |
| Non-scraped | |
| Bad sectors | |
| Bad areas | |
| Read errors | |
| Final ddrescue status | |

**SHA-256 Integrity Record:**

- Hash generated: Yes / No / Unknown
- Hash algorithm:
- Hash record retained: Yes / No / Unknown
- Hash generation stage: Initial acquisition / Post-acquisition / Other

**If not applicable:**

N/A — logical-only case (no imaging performed).

Goal: Always image first unless the case is confirmed logical-only and low-risk.

---

## 📂 Evidence Collected

*(Only generic / non-sensitive artifacts should be saved.)*

| Artifact | Status |
|---|---|
| device-info.txt | Retained / Lost / Not collected |
| smartctl.txt | Retained / Lost / Not collected |
| hdparm.txt | Retained / Lost / Not collected |
| lsblk.txt | Retained / Lost / Not collected |
| fdisk.txt | Retained / Lost / Not collected |
| SHA-256 record | Retained / Lost / Not collected / Unconfirmed |
| Cropped screenshots | Retained / Lost / Not collected |
| ddrescue mapfile (if applicable) | Retained / Lost / N/A |

*(Actual recovered client files are NEVER stored in the public repository.)*

---

## 🗂 Evidence Summary

All public evidence stored under:

`/cases/YYYY-NN-<case-name>/evidence/`

Example contents:

- DMDE scan screenshots
- Partition maps
- SMART assessment screenshots
- ddrescue progress screenshots
- Sanitized hardware artifacts
- Imaging logs and acquisition records, where appropriate

All evidence must be reviewed and sanitized before publication.

---

## 🧰 Recovery Actions

*(Write in short, factual bullet points.)*

**Tools Used:**

- 

**Order of Operations:**

1.
2.
3.

**Acquisition Method:**

- Imaging first / Live-disk work / N/A

**Recovery Methods:**

- Metadata-based recovery
- Filesystem reconstruction
- Partition recovery
- Signature-based carving
- Selective file extraction
- Other:

**Verification Method:**

- Metadata inspection
- File signature inspection
- OS-generated thumbnails
- Container / file structure inspection
- Client-authorized playback or content verification
- Not performed

*(Include only methods actually used.)*

---

## 📦 Output / Result

**Imaging Acquisition Result:**

**File Recovery Result:**

**Recovered Data Volume:**

**Recovered File Count:**

**Hierarchy Preserved:** Yes / Partial / No

**Carving Required:** Yes / No

**Client Goals Met:** Yes / Partial / No / Pending

**File Verification Outcome:**

**Known Limitations:**

*(Distinguish successfully imaged sectors from successfully recovered and verified client files.)*

---

## ⏱ Time Breakdown

| Stage | Duration |
|---|---|
| Initial diagnostics | |
| Imaging (ddrescue) | |
| Filesystem / partition analysis | |
| Metadata-based recovery | |
| Signature carving | |
| Manual extraction / recovery | |
| Verification | |
| Final transfer & packaging | |

**Total Analyst Time (active):**

**Calendar Duration:**

---

## 🔒 Privacy Notes

- No client names or identifying information are published.
- No private folder names or directory listings are published.
- No actual recovered client files are stored.
- No private file previews or identifiable content are shown.
- Diagnostic artifacts and screenshots are sanitized before publication.

---

## 🧭 Reflection / Lessons

*(Short bullet list — what changed in your thinking.)*

- 
- 
- 

---

## ✔ Next Time I Will

(One sentence improvement commitment.)

---

(End of Case Record — do not attach recovered client content.)
