# Case ID
YYYY-NN (increment each case)

# Media
Model:
Capacity:
Interface (USB/SATA/NVMe):
Serial (first 4 chars only):

# Symptoms Observed
• Slow reads / clicking / SMART warnings / disappears / etc

# Failure Signature
(e.g., bad band at 1.2TB mark, metadata collapse, missing MFT, broken partition)

# Acquisition Log
Raw ddrescue mapfile: `ddrescue.log`

Commands used:
```
ddrescue -f -n /dev/sdX image.img map.log
ddrescue -f -r1 /dev/sdX image.img map.log
```

# Disk Evidence
• device-info.txt  
• smartctl.txt  
• hdparm.txt  
• lsblk.txt  
• fdisk.txt  

# Result
Percent recovered:
Hierarchy preserved: yes/no/partial
Carving required: yes/no

# Time Required
Imaging:
Analysis:

# Notes
• Short bullet points only

# What I'll do earlier next time
(short sentence)
