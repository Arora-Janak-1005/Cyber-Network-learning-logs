# Digital forensics
## Golden Rules:
- You do not change the state of the Machine.
- Maintain Chain of Custody (report of what you do and that you submit to the court) because you are liable by Lab(scrutanisable) 
#### *Responder Actions*
1. Scene stablization: Control the chaos. Tell everyone in the organization to step away fom their keyboards and their devices.
2. Analyze who all have access to what.
3. record everything.
4. Image the main memory(RAM) first , because ongoing processes and attacks, decrypted data that was never saved , N no. of things are possible in the ram and not imaging that first could destroy evidence.
5. Isolate the risk or keep it alive.
---
### Lecture 1:
- cyber crime varies from jurisdiction to jurisdiction and between jurisdictions so everyone has a different definition.
- using comp. & net as a integral component of the crime is called cyber crime.
- Computer espionage: damaging someone's computer either hardware or software.
- every org have a CIRT team i.e cybercrime investigation and || team
- you need to work according to the policy of the organization and the jurisdiction and 
### Pyramid Scheme:
- when you are asked to buy a membership and you are asked to ask other members to join and pay you...so the perpetrator gets more and more money. 
- these are banned by the law over the network.
- morris worm : a program created by morris , it expand over the network over many countries .
- PONZI PYRAMID: double the money in one month.
- people fall more and more by investing more in this.
- unregulated deposit schemes act 2019
---
## Lab1: 
- Very fir step is disk imaging - process of copying data from compromised machine bit by bit- because we do not work with orignal disk before the orignal machine is confiscated
- during a bad sector it is notified and its either skipped or the tool stops at the very step
- 0 sector contains the master boot records
- partition tables (read file structures of FAT32 , ntfs, Xfat)
- two tools ftk imager(gui tool)(large company FTK), Not yet told


---
## Lab 2:
tools learnt today: dcfldd,dc3dd,dd,guymager
### File system:
id type:
07 ntfs
0b fat
83 

DC# tools:
DC3 DD 
specialize for forensics for computing hashes

-  by computing hash we can show that the image copy is exact


DC3DD:
if == give input file.
if=/dev/sdb
of == output file
of= pd_image5.dd
ofsz=25MB => split it into file size
 ofs=z_split1.00 naming of splits...it automatically increase number of segments after the set amount.
concatinate at the destination : "cat z_split1.* | dc3dd of = z_combined"

- hash = sha1 0r md5 || hofs you can calculate the hashes of each split.
- wipe => this command wipes or writes the whole destination hard drive so that we can create a forensics sterile hdd.
- you can also give patterns pat=000.
- you can do device to device as well
### dd tool:
- it does not show but it is doing its job, used in the field as a professional tool.
- if =/dev/sdb of=mbr55(master boot record) bs=512 count=1 conv=noerror,sync
- noerror to continue reading, dd always stops at bad sector so it is important
- sync simple insert 0 and move forward

---
===
## Lecture 2:
### violent cyber crimes : 
- swatting, doxxing,child porn,cyber stalking.
- Swatting:

### Non violent cybercrime:
- Cybertrespass: just scanning the network ; an act did without authorization but does not threaten or damage any data.

- using comps to steal information , money, and other valuables is cybertheft.
- embezzlement: someone from inside organization with access misusses the info they have.
- unlawful appropriation: someone from outside 
- use comps to steal trade secrets, client lists, etc. is corporate espionage.
- INSIDER TRADING: knowing about growth so you buy the stocks, using insider knowledge for personal gain.
- sabotaging business by hiring someone from the opoosing business (dnc leak cases- us president case.)
- plagirism: someone else's work as our own. someone can take you to court
- piracy: unautorized copy of copyrighted goods.france and canada are very strict on this.
- identity theft: someone else's identity is being used for mal or otherwise stealing it.
- dns cache poisoning.
- hpin3- malicious spoofed packets over the network.
- http flood attack : sending vast amount of http get or post.
- slowloris attack: sending incomplete http request.
- dns amplification: too large response of dns replies fills the memory of the victim, the victim becomes overwhelmed.
- Ping of death: 
- teardrop attack: Dos attack: overlapping fragments: the target system fails to recombine them: causes segmentation faults.
- Smurf: uses the broadcast address , flood the broadcasts to a victim machine
- cyberfraud: chaning records, transaction manipulation.
- extraneous transaction: manipulation of transaction without the authorizationa dn know how of the client.
- cyber squatting: using the good will of another company for advantage.
- nielitcyberforensics.in(practice forensics) 
- yale university model.
- configuration of the windows is stored in registry.
---
## LAB 3:
* Command Used For Windows*
- wmic disdrive list brief
#### dd --list (command to find out the partitions on a device)
- service.msc
- Add-WindowsCapability -Online -Name OpenSSH.Server
---
## LAB 4:
- forensic (Feb 2nd, 26)  - 

- tool - foremost
- garykessler for file extentions and header and footer information

- process :
- first make a new folder foremost then use the foremost tool to uncomment the required file to find from the image file(pendrive) , then put the command containing the ext, case, size, header, footer.
- feh *. jpeg to view 

- Tool - Scalpel
- Tool - Recoverjpeg
- Tool - bulk-extractor
- Tool - magicrescue
---
## LEC 3:
- Accidental and situational cybercriminals
- crime victims (to whom the crime has actually happened)
- Victimology
- jumpers on hdd on scuzy interface was used to set a master slave setting.
---
## Chapter 5 of shinder L.D book:
- any evidence without permission is not admissible in the court.
- the victim can submit a proper concreat evidence to invoke an investigation.
- the evidence should be persuadable.
- we can only check the authenticity via hash check.
- maintain chain of custody.
- ***write blockers*** both of hardware and software
---
Lab: 
- tools like foremost and scapel extract ram data from the image, which cases loss of metadata of the files so to defend that tools like sleuthkit and autopsy are used.
- sleuthkit is a set of binaries.
- imgstat tells the seize of the file and sector
-how memory has been laid out in the image. (mmstat) here dos partitioning scheme.
- gpt and dos partitioning scheme , legacy supports dos, uefi supports gpt.
- mmstat -i list.
- ENCASE IS ALSO TOOL LIKE FTK.
- mmstat -t list (partitioning scheme)
- mmls(memory list)
- in the first sector os the harddrive i.e. master boot record.
- we use a hexeditor to read those first sectors created 
- aa55 or 55aa is the ending signature of the mbr.
- volume boot record.
- every volume has their first sector .
hardisk ka first sector and volume ke first sector me difference hai then the boot code in tjhe mbr runs to point to the required 
- data pointed by the partition is
- cyliinder head and sector (chs) 
- logical block addresses (lba) offset, which address the data is saved, 
- sleuthkit shows in decimal not hexadecimal.
- fsstat -o 8064(offset) <imgfile> 
- fls -o  offset > to see the content like ftk
- r/r is regular file, d/d is directories ,* represents deleted files
- fls -d switch to list deleted files.
- tsk_recover  -o offset -e <filename> for recovery of the data.
- testdisk (fs reader)
- icat command to see the files (read) without recovery, but it doesnt show anything but binaries, so its basically just to check for empty file or not

---
## Refrences :
1. Shinder L. D., Cross M., Scene of the Cybercrime, Syngress (2008) 2nd ed.
2. Marcella J. A. and Guillossou F., Cyber Forensics: From Data to Digital Evidence, Wiley (2012).
3. Nina Godbole, Sunit Belapure, Cyber Security, Wiley (2011)
