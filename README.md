\# Deleted File Recovery Investigation



\*\*Digital Forensics | FTK Imager | Autopsy | Windows 11\*\*



\## 1. Project Overview



This project demonstrates a practical digital forensics investigation focused on identifying deleted files from a storage device.



The investigation was performed in a controlled environment using a 2 GB virtual disk configured as an NTFS volume. Sample files were added to the disk, and two files were deliberately deleted to simulate a situation in which an employee accidentally or intentionally deletes potentially important company data.



The virtual disk was acquired using \*\*FTK Imager\*\* to create a forensic image. The acquired image was then loaded into \*\*Autopsy\*\* for examination. The analysis focused on identifying deleted file entries and examining the information available about them.



The purpose was to understand how forensic investigators acquire digital evidence and examine a storage image for traces of deleted files.



\## 2. Investigation Scenario



Imagine an employee has deleted some files from a company storage device. These files may contain confidential notes or employee information.



Even after files are deleted, information about them may remain in the file system or their contents may remain in unallocated storage space, depending on the file system and whether the data has been overwritten.



A digital forensic investigator may examine a forensic image of the storage device to identify traces of deleted files and determine whether their contents can be recovered.



This project recreates that situation using sample data and a virtual storage device.



\## 3. Project Objectives



\- Create a controlled storage environment for the investigation.

\- Simulate the deletion of selected files.

\- Acquire a forensic image using FTK Imager.

\- Verify the integrity of the acquired image using the tool's verification process.

\- Load the forensic image into Autopsy.

\- Identify deleted file entries.

\- Examine the available metadata and details of deleted files.

\- Document the investigation process and findings.



\## 4. Tools and Technologies Used



| Tool / Technology | Purpose |

|---|---|

| Windows 11 | Investigation environment |

| Windows Disk Management | Creation and configuration of the virtual disk |

| FTK Imager | Forensic image acquisition and verification |

| Autopsy | Examination and analysis of the forensic image |

| NTFS | File system used on the virtual disk |

| E01 | Forensic image format |



\## 5. Investigation Environment



The investigation was conducted using a virtual storage device rather than a personal USB drive. This provided a controlled environment in which files could be created and deleted without affecting important personal data.



\*\*Storage device details:\*\*



| Parameter | Details |

|---|---|

| Device type | Virtual hard disk |

| Storage capacity | 2 GB |

| File system | NTFS |

| Partition style | MBR |

| Operating system | Windows 11 |

| Imaging tool | FTK Imager |

| Examination tool | Autopsy |

| Image format | E01 |



\## 6. Evidence Preparation



A 2 GB virtual hard disk was created using Windows Disk Management.



The disk was initialized, configured with an MBR partition style, and formatted using the NTFS file system.



Four sample files were prepared and copied to the virtual disk:



| File Name | Description |

|---|---|

| confidential\_notes.txt | Sample confidential notes |

| employee\_records.csv | Sample employee records |

| project\_report.txt | Sample project information |

| sample\_image.jpg | Sample image file |



These files were used as test evidence for the investigation. They did not contain actual company or personal information.



\*\*Screenshot – Virtual disk and original sample files\*\*



!\[Screenshot placeholder](Screenshots/02\_virtual\_disk.png)



\## 7. Simulating File Deletion



To recreate the investigation scenario, two sample files were deleted from the virtual disk:



\- confidential\_notes.txt

\- employee\_records.csv



The other two files were kept on the disk:



\- project\_report.txt

\- sample\_image.jpg



This created a situation where the storage device contained both existing files and traces of deleted file entries.



The deletion was performed intentionally for testing purposes.



\*\*Screenshot – Files remaining after deletion\*\*



!\[Screenshot placeholder](Screenshots/03\_remaining\_files.png)



\## 8. Forensic Image Acquisition Using FTK Imager



After preparing the virtual disk and deleting the selected files, a forensic image was created using FTK Imager.



A forensic image is a bit-by-bit copy of a storage device or selected evidence source. It allows investigators to examine a copy of the evidence instead of repeatedly working with the original source.



\### Acquisition procedure



1\. Opened FTK Imager.

2\. Selected the option to create a disk image.

3\. Selected the virtual disk as the evidence source.

4\. Chose the E01 image format.

5\. Specified the destination for saving the forensic image.

6\. Started the image acquisition process.

7\. Waited for the acquisition to complete.

8\. Checked the verification result.



\### Acquisition result



The forensic image was successfully created in E01 format.



The image was split into two segments:



\- Employee\_USB\_Forensic\_Image.E01

\- Employee\_USB\_Forensic\_Image.E02



Both segments belong to the same forensic image and must be kept together.



FTK Imager displayed \*\*Match\*\* as the verification result.



This indicated that the verification performed by FTK Imager matched the acquired image against its source during the acquisition process.



\*\*Screenshot – FTK Imager acquisition configuration\*\*



!\[Screenshot placeholder](Screenshots/04\_ftk\_acquisition.png)



\*\*Screenshot – Successful image verification\*\*



!\[Screenshot placeholder](Screenshots/05\_image\_verification.png)



\*\*Screenshot – Created forensic image segments\*\*



!\[Screenshot placeholder](Screenshots/06\_forensic\_image\_created.png)



\## 9. Forensic Image Examination Using Autopsy



After acquisition, the E01 forensic image was opened in Autopsy for further examination.



Autopsy is a digital forensics platform used to examine storage images and investigate file system information, existing files, deleted entries, and other digital evidence.



\### Examination procedure



1\. Opened Autopsy.

2\. Created a new case for the investigation.

3\. Added the forensic image as a data source.

4\. Selected the E01 image file.

5\. Allowed Autopsy to process the data source.

6\. Examined the file system and available file listings.

7\. Located the deleted file entries.

8\. Opened the available details for the deleted entries.



\### Examination result



Autopsy successfully loaded and processed the forensic image.



The deleted entries corresponding to the files removed during the simulation were visible during the examination.



The available file details could also be inspected in Autopsy.



This demonstrated that deleted file entries could still be identified in the examined forensic image.



\*\*Screenshot – Forensic image loaded in Autopsy\*\*



!\[Screenshot placeholder](Screenshots/07\_image\_loaded\_autopsy.png)



\*\*Screenshot – Deleted file entries identified\*\*



!\[Screenshot placeholder](Screenshots/08\_deleted\_files\_identified.png)



\*\*Screenshot – Details of deleted file entries\*\*



!\[Screenshot placeholder](Screenshots/09\_deleted\_file\_details.png)



\## 10. Investigation Findings



The investigation produced the following results:



| Investigation Activity | Result |

|---|---|

| Virtual disk creation | Successful |

| File preparation | Four sample files created and copied |

| File deletion simulation | Two files deleted |

| Forensic image acquisition | Successful |

| Image format | E01 |

| Image segments | E01 and E02 |

| FTK Imager verification | Match |

| Autopsy image loading | Successful |

| Deleted file identification | Deleted entries visible |

| Deleted file details | Available details examined |



\### Key observations



1\. A forensic image could be created from the prepared virtual disk using FTK Imager.

2\. The acquisition verification result was Match.

3\. Autopsy was able to load and examine the acquired image.

4\. Deleted file entries were visible during the examination.

5\. Information available for deleted entries could be inspected.



\## 11. Limitations



This project focused on forensic image acquisition and deleted file identification.



The visibility of a deleted file entry does not necessarily mean that its complete contents can be recovered.



Successful recovery depends on several factors, including whether the original data has been overwritten, the file system's behavior, and the condition of the storage device.



This investigation confirmed the visibility of deleted entries in Autopsy. It did not establish that the complete contents of both deleted files were successfully recovered and verified.



The investigation was performed using a virtual disk and sample files, not a real company storage device.



\## 12. Conclusion



This project provided practical experience in the basic digital forensics investigation process.



A controlled file deletion scenario was created using a virtual storage device. The device was acquired using FTK Imager, and the resulting E01 image was examined using Autopsy.



The examination showed that deleted file entries could still be identified in the forensic image and that available details could be inspected.



The project helped demonstrate the importance of forensic image acquisition, verification, evidence examination, and proper documentation during a digital investigation.



\## 13. Skills Demonstrated



\- Digital Forensics Fundamentals

\- Forensic Image Acquisition

\- Evidence Integrity Verification

\- Deleted File Identification

\- File System Examination

\- FTK Imager

\- Autopsy

\- NTFS File System

\- Digital Evidence Documentation



\## 14. Repository Structure



```text

Deleted-File-Recovery-Investigation/

│

├── README.md

│

└── Screenshots/

&#x20;   ├── 01\_source\_files.png

&#x20;   ├── 02\_virtual\_disk.png

&#x20;   ├── 03\_remaining\_files.png

&#x20;   ├── 04\_ftk\_acquisition.png

&#x20;   ├── 05\_image\_verification.png

&#x20;   ├── 06\_forensic\_image\_created.png

&#x20;   ├── 07\_image\_loaded\_autopsy.png

&#x20;   ├── 08\_deleted\_files\_identified.png

&#x20;   └── 09\_deleted\_file\_details.png

```



\---



\*\*Disclaimer:\*\* This project was conducted in a controlled learning environment using sample data and a virtual disk. It is intended for educational and portfolio purposes.

