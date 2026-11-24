
# Deleted File Recovery Investigation

## Project Overview

This project demonstrates a basic digital forensics investigation involving deleted file identification and recovery analysis.

A virtual USB drive was created to simulate a situation where an employee deletes confidential files. The drive was then acquired using **FTK Imager**, and the forensic image was examined in **Autopsy** to identify deleted file entries and inspect their details.

## Objectives

- Create a virtual disk to simulate a USB storage device.
- Add sample files to the virtual disk.
- Simulate deletion of selected files.
- Create a forensic image using FTK Imager.
- Verify the acquired forensic image.
- Analyse the image using Autopsy.
- Identify deleted files and examine their available details.

## Tools Used

| Tool | Purpose |
|---|---|
| FTK Imager | Forensic image acquisition and verification |
| Autopsy | Forensic examination and deleted file analysis |
| Windows Disk Management | Creation and configuration of the virtual disk |

## Investigation Environment

| Parameter | Details |
|---|---|
| Operating System | Windows 11 |
| Virtual Disk Size | 2 GB |
| File System | NTFS |
| Disk Label | EMPLOYEE_USB |
| Image Format | E01 |
| Forensic Analysis Tool | Autopsy |

## Investigation Process

### 1. Creating the Virtual Evidence Disk

A 2 GB virtual hard disk was created using Windows Disk Management. It was initialized, formatted with the NTFS file system, and assigned a drive letter.

This virtual disk was used as the evidence source to avoid experimenting with a physical USB drive containing important data.

**Screenshot – Virtual Disk Configuration**

![Virtual Disk](screenshots/01_virtual_disk.png)

### 2. Creating Sample Files

Four sample files were prepared and copied to the virtual disk:

- `confidential_notes.txt`
- `employee_records.csv`
- `project_report.txt`
- `sample_image.jpg`

These files represented ordinary employee and company-related data.

**Screenshot – Original Sample Files**

![Original Files](screenshots/02_original_files.png)

### 3. Simulating File Deletion

To simulate a data deletion incident, the following two files were deleted:

- `confidential_notes.txt`
- `employee_records.csv`

The other two files were left on the virtual disk.

**Screenshot – Files Remaining After Deletion**

![Remaining Files](screenshots/03_remaining_files.png)

### 4. Forensic Image Acquisition Using FTK Imager

FTK Imager was used to create a forensic image of the virtual disk.

The image was saved in E01 format. The acquisition generated two image segments:

- `Employee_USB_Forensic_Image.E01`
- `Employee_USB_Forensic_Image.E02`

Both segments were retained together because they form part of the same forensic image.

After acquisition, the image verification result displayed **Match**.

This indicated that the verification performed by FTK Imager was successful.

**Screenshot – FTK Imager Acquisition**

![FTK Acquisition](screenshots/04_ftk_acquisition.png)

**Screenshot – Image Verification Result**

![Verification](screenshots/05_verification.png)

### 5. Examining the Image in Autopsy

The acquired E01 image was loaded into Autopsy as a data source.

The forensic image was analysed to examine its file system contents and identify deleted file entries.

Autopsy displayed the deleted file entries, including details associated with the deleted files.

**Screenshot – Image Loaded in Autopsy**

![Autopsy Data Source](screenshots/06_autopsy_image.png)

**Screenshot – Deleted Files Identified**

![Deleted Files](screenshots/07_deleted_files.png)

**Screenshot – Deleted File Details**

![Deleted File Details](screenshots/08_deleted_file_details.png)

## Investigation Findings

The investigation demonstrated that deleted file entries could still be identified during forensic examination of the acquired image.

| File Name | Action Performed | Observation |
|---|---|---|
| confidential_notes.txt | Deleted | Deleted file entry visible in Autopsy |
| employee_records.csv | Deleted | Deleted file entry visible in Autopsy |
| project_report.txt | Retained | Present on the virtual disk |
| sample_image.jpg | Retained | Present on the virtual disk |

### Key Observations

- A forensic image of the virtual disk was successfully created using FTK Imager.
- FTK Imager reported a successful verification result (`Match`).
- The E01 image was successfully loaded into Autopsy.
- Autopsy displayed the deleted file entries.
- Deleted file details could be examined during the analysis.

**Note:** Identifying a deleted file entry does not automatically mean its complete contents have been recovered. This project documents the deleted entries observed in Autopsy. Successful file recovery should only be claimed if the files were actually exported and their contents verified.

## Limitations

- The investigation was performed using a simulated 2 GB virtual disk rather than a physical USB device.
- The results depend on the available file system metadata and data present in the acquired image.
- The visibility of a deleted file entry does not guarantee that its original contents are fully recoverable.

## Conclusion

This project provided practical experience with the basic digital forensic investigation process, from preparing an evidence source and simulating file deletion to acquiring a forensic image and examining it using Autopsy.

The investigation showed how forensic tools can help identify deleted file entries and examine available file details even after deletion.

## Skills Demonstrated

- Digital Forensics Fundamentals
- Forensic Image Acquisition
- FTK Imager
- Autopsy
- Deleted File Analysis
- NTFS File System Examination
- Evidence Handling and Verification
- Forensic Documentation

---

## Repository Structure

```text
Deleted-File-Recovery-Investigation/
│
├── README.md
│
├── screenshots/
│   ├── 01_virtual_disk.png
│   ├── 02_original_files.png
│   ├── 03_remaining_files.png
│   ├── 04_ftk_acquisition.png
│   ├── 05_verification.png
│   ├── 06_autopsy_image.png
│   ├── 07_deleted_files.png
│   └── 08_deleted_file_details.png
│
└── Evidence/
    ├── Employee_USB_Forensic_Image.E01
    └── Employee_USB_Forensic_Image.E02
```

**Note:** The repository structure above is a suggested organisation. Keep the Evidence folder out of GitHub if the image files are large or contain sensitive data. The screenshots folder and filenames in this README must match your actual repository.


