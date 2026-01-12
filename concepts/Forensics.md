## Digital forensics
# Golden Rules:
- You do not change the state of the Machine.
- Maintain Chain of Custody (report of what you do and that you submit to the court) because you are liable by Lab(scrutanisable) 
# Lecture 1:
- cyber crime varies from jurisdiction to jurisdiction and between jurisdictions so everyone has a different definition.
- using comp. & net as a integral component of the crime is called cyber crime.
- Computer espionage: damaging someone's computer either hardware or software.
- every org have a CIRT team i.e cybercrime investigation and || team
- you need to work according to the policy of the organization and the jurisdiction and 
# Pyramid Scheme:
- when you are asked to buy a membership and you are asked to ask other members to join and pay you...so the perpetrator gets more and more money. 
- these are banned by the law over the network.
- morris worm : a program created by morris , it expand over the network over many countries .
- PONZI PYRAMID: double the money in one month.
- people fall more and more by investing more in this.
- unregulated deposit schemes act 2019

## Lab1: 
- Very fir step is disk imaging - process of copying data from compromised machine bit by bit- because we do not work with orignal disk before the orignal machine is confiscated
- during a bad sector it is notified and its either skipped or the tool stops at the very step
- 0 sector contains the master boot records
- partition tables (read file structures of FAT32 , ntfs, Xfat)
- two tools ftk imager(gui tool)(large company FTK), Not yet told

## Refrences :
1. Shinder L. D., Cross M., Scene of the Cybercrime, Syngress (2008) 2nd ed.
2. Marcella J. A. and Guillossou F., Cyber Forensics: From Data to Digital Evidence, Wiley (2012).
3. Nina Godbole, Sunit Belapure, Cyber Security, Wiley (2011)


## Lab 2:
tools learnt today: dcfldd,dc3dd,dd,guymager
ofsz=25MB => split it into file size
 ofs=z_split1.00 naming of splits...it automatically increase number of segments after the set amount.
concatinate at the destination : "cat z_split1.* | dc3dd of = z_combined"

- hash = sha1 0r md5 || hofs you can calculate the hashes of each split.
- wipe => this command wipes or writes the whole destination hard drive so that we can create a forensics sterile hdd.
- you can also give patterns pat=000.
- you can do device to device as well
# dd tool:
- it does not show but it is doing its job, used in the field as a professional tool.
- if =/dev/sdb of=mbr55(master boot record) bs=512 count=1 conv=noerror,sync
- noerror to continue reading, dd always stops at bad sector so it is important
- sync simple insert 0 and move forward
