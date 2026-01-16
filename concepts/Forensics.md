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
## File system:
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
# dd tool:
- it does not show but it is doing its job, used in the field as a professional tool.
- if =/dev/sdb of=mbr55(master boot record) bs=512 count=1 conv=noerror,sync
- noerror to continue reading, dd always stops at bad sector so it is important
- sync simple insert 0 and move forward


## Lecture 2:
- violent cyber crimes : swatting, doxxing,child porn,cyber stalking.
- Swatting:

# Non violent cybercrime:
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
- 