# Threat Hunting
---
- Threat hunting by definition according to me is the process of recoganizing patterns that the attackers use to infilterate the systems.
- threat hunting is majorly of two types the proactive and the reactive.
#### Proactive: 
in which there is a team and they are actively searching for patterns and signatures of different attacks.
In a process  called **THE HUNT**
hunt is basically the timeline following left of the **boom** to before the alarms are triggered,right of the boom.
##### Reactive:
as the name suggest, we react to he situation, meanning someone just told us that we are being attacked(by the IDS or AV alert or FBI), now this time could already be when some attack has already started, before the alarms are triggered.
##### The boom:

it is the point when the attack has begun effecting the systems.
Left of the boom: it is the time period spend by the attacker, doing recon.
Right of the boom: it is the recovery of the system. **according to ponemon institute's survey the mean time to identify(MTI) is ~200 days for identifying the problem and Mean time to contain(MTC)~70 days for recovery.**
---
### Threat hunting as a process:
We need to see alot of things in order to hunt that are based on experience,signatures and hunches:
- Indicators of compromise: a small hole here and a small holes there.
- Indicators of attack: probing, or other indicators.
- Intel feeds: the latest attacks going on around the world , intelligence we can consume from things going on in the environment, certain vlns going on, the geography where they are going on.
- Vulneabiliies scan: what the attacker is seeing we do that so that we can know our own, weakness.
now, an intelligent threat hunter will connect these isolated points and will be able to make out that this is a pont of breach
### Tools used by threat hunters:
- XDR :extended detection and response capability[[]]
- SIEM :security information and event management[[]]
- UBA :user behaviour analytics[[]]
compile their result to AI.
---
### Approach of threat hunting:
#### "target centric"
- start by evaluating the internal project, what is valuable that the attacker might want to compromise.
- after knoeing the project unicorn, know the systems involved , the people involved 
the main challenge herre is to know the organization as whole, well enough to recoganize what is important and what is not.
TIP: "collaborate with any high auth, this makes  this process easy."
#### Actor centric:
- Rather than focusing on he potential target, the hunt tam develops an actor intelligence of who might want to attack the industry.
this can be done either by self research or 3rd party tips, to identify specific actors 
- powerful approach but requires knowledge o eho ight want t attack you.
- threat intellgience firms may flag alot of actors , but only a few are those which might be relevant to u.


---
## References:
Medium: https://sroberts.medium.com/incident-response-is-dead-long-live-incident-response-5ba1de664b95

IBM Technology yt channel :https://www.youtube.com/watch?v=VNp35Uw_bSM

Threathunting.net: https://www.threathunting.net/reading-list
---
