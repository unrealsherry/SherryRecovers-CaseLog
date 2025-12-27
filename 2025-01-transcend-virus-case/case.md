# Case Report – Transcend External HDD (Logical Damage – Virus Hidden Data)

**Client:** Personal – anonymized  
**Case ID:** 2024-01  

**Drive Model:** Transcend StoreJet  
**Capacity:** 1TB  
**Interface:** USB 3.0  
**Serial (first 4 chars only):** Not exposed over USB (external enclosure – S/N unavailable)  

**Failure Category:** Logical damage – malware-induced folder concealment  
**Outcome:** 100% successful recovery (hierarchy rebuilt manually)  

**Total Analyst Time (active):** ~12–14 hours  
**Calendar Duration:** ~4–5 days (intermittent due to manual rebuild)

---

## 🧩 Incident Summary
Client delivered a 1TB Transcend external HDD where all known personal data appeared "gone".  
Windows Explorer showed empty high-level folders (“Pictures, Movies, Projects”), while original folders were **hidden and replaced** by fake empty decoy directories — a common pattern in USB-propagating malware.

The drive itself was mechanically healthy. This was **not** a physical or filesystem failure — it was an **infection that modified folder attributes and replaced visible directories with empty ones**.

---

## 🛠 Actions Taken

### 1️⃣ Initial Assessment
| Task | Result |
|------|--------|
| Windows mount check | Volume mounted normally – 1x single 1TB NTFS partition |
| Visual folder check | Only empty fake folders visible (`Pictures`, `Movies`, etc.) |
| Malware scan | Performed immediately before touching data |
| Attrib attempts | `attrib -h -s` and attribute toggles failed to restore visibility |

Reason: Malware changed folder attributes in a way that Windows Explorer does **not** easily revert.

---

### 2️⃣ Logical Data Recovery
Performed recovery using DMDE **on the live disk** (acceptable for logical-only cases).

DMDE identified:
- Full original directory tree
- All hidden folders + internal hierarchy
- No metadata loss
- All files fully readable

📌 Because DMDE Free cannot mass-extract folders, extraction was performed **manually** — directory-by-directory, rebuilding original paths.

Result:

✔ All hidden folders recovered  
✔ File hierarchy reconstructed by hand  
✔ 1:1 original structure re-created  

---

### 3️⃣ Client Delivery
Recovered contents were temporarily staged on analyst’s personal storage **with explicit consent**, then:

- Drive was completely formatted (**zero-write**)
- Data was copied back **exactly as originally structured**
- No client data is retained after hand-off

🔐 Privacy stance:
All temporary data storage was short-term, controlled, and destroyed immediately after delivery.

---

## ⏱ Time Breakdown
| Stage | Duration |
|--------|----------|
| Imaging (ddrescue) | N/A – logical case (no physical risk) |
| Malware scan & assessment | ~1 hour |
| Manual extraction & hierarchy rebuild | ~10–12 hours |
| Formatting & final data transfer | ~1–2 hours |

**Total Analyst Time (active):** ~12–14 hours  
**Calendar Duration:** ~4–5 days (intermittent work & availability gaps)


---

## 📦 Final Deliverables
- ✔ Malware removed
- ✔ 100% of hidden data restored
- ✔ Fully rebuilt directory structure
- ✔ External drive returned to clean usable state


(No recovered content or file previews are kept or uploaded.)

---



## 🧭 Reflection / Lessons (for skill-growth tracking)
| Observation | Learning |
|-------------|----------|
| Logical-only infections can look like "data loss" | Always rule out malware before filesystem conclusions |
| Manual rebuild via DMDE Free is extremely time-expensive | Future: use licensed tool or scripted copy to save hours |
| Temporary client-data staging is a liability | Must replace with dedicated offline recovery disk + wipe policy |

> _This case reinforced a critical lesson: logical failures can present like physical loss. 
The success came not from tools — but from patience, discipline, and controlled workflow._

---

## 🧾 Consent
Client verbally consented to temporary staging and anonymized record of this case. 
No identifiable names, directory names, or content are published.

