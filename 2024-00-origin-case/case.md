# Case Report – Hitachi 1TB HDD (Prod. Dec 2010)

**Client:** (Personal friend – anonymized)  
**Drive:** Hitachi – 1.0TB – Production Date: Dec 2010  
**Failure Status:** Severe degradation – Health Reported: **0% (Hard Disk Sentinel)**  
**Outcome:** **Partial File Recovery** + Full Raw Disk Image Delivered  
**Total Time Spent:** ~4–6 days (Imaging + Recovery Attempts)

---

## 🧩 Incident Summary
A client-owned external HDD (1TB Hitachi, manufactured Dec-2010) was delivered after becoming unreadable inside Windows.  
Windows attempted **automatic repairing at boot**, but failed; file explorer only displayed **2 readable partitions** and **1 corrupted/mangled partition** inaccessible to the user.

The drive exhibited extreme read-instability. SMART flags indicated imminent failure; **imaging was prioritized** instead of filesystem repair to avoid further degradation.

---

## 🛠 Actions Taken

### 1️⃣ Initial Assessment
| Task | Result |
|------|--------|
| Non-invasive physical check | Drive body and SATA connector inspected externally. No opening of the drive or PCB removal was performed. |
| SMART / HDSentinel | **0% Health** – reallocated and bad sectors present |
| lsblk / disk list check | Confirmed 3 partitions, 1 corrupted |
| Decision | Proceed with **full bit-level image** before touching disk |

---

### 2️⃣ Imaging Procedure
Performed full-disk image of the failing drive using a rescue-safe environment (**SystemRescueCD live env**).  
Imaging required **multiple days** due to:
- read freezes
- unstable sectors
- retries + fallback read mode

Final image size: **~1 TB (raw .img)**  
Image handed to client for future preservation + optional lab-grade recovery if desired.

---

### 3️⃣ Data Recovery Attempts (Soft-Layer)
Using **DMDE**, the following recovery paths were attempted on the image:
- Metadata-based scan
- File signature scan
- Partial NTFS reconstruction

Recovered identifiable material included:
- Thousands of graphics/images (JPG, PSD, PNG…)
- Text & document files
- Some executables and application folders
- Misc. small files

⚠️ Folder-level naming structure was heavily inconsistent due to metadata collapse.  
A **partial extraction** (not structured) was possible, however most of the *clean full-directory tree* could not be restored.

---

## 📦 Final Client Deliverables
- ✔ Full 1TB Raw Disk Image (`*.img`)
- ✔ Screenshots documenting DMDE scans
- ❌ Full clean directory-level restoration (not possible due to metadata loss)

Client retained **all rights** to request future advanced lab-grade service if deeper reconstruction is desired.

---

## 🔒 Notes on Privacy & Evidence
- No personally identifiable directory names or file previews are published
- Images included in repository are **cropped** to general UI-only screenshots
- Raw client data is **never stored** in repo (only documentation + neutral evidence)

---

## 🧾 Lessons Learned / Takeaways
| Observation | Lesson |
|-------------|--------|
| Imaging before touching filesystem | Saves data when drive is dying |
| 0%-health drives behave unpredictably | Time investment can multiply ×10 |

---

> _This case was taken as an early-stage learning opportunity. I accepted a small compensation to cover time and machine occupation._
  
---

