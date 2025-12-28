## Learning the OWASP top 10 2021
- open web application security project(owasp) top 10 vulnerabiliteis for web apps. publishes every 3 years.

## A01: Broken access control
- Access Control - acess control is giving different levels of authorization to different users, basically who has what permissions to do in an organization.
- vulnerbilities that allows an unauthorized person to access certain functtionality that they are not allowed is broken access control.
## A02: Cryptographic Failure
- Cryptography - is an art or mechannism to change a pllain text to encrypted form. so that the confidencial information cant be read by unauthorized ppl
- info not encrypted properly is cryptographic failure.
- vuln caused due to misuse or lack of use of cryptographic algorithms is called crypto failure.
- data in transit and data at rest
## A03: Injection
- vul caused due to  unsanitized user inputs , meaning the application is fed input such that it interprets it as a command or parameter rather than the data
- these highly depend on the technologies that are being used and how these technologies interpret something.
- two types majorly : sql injecction and command injection
- Sql injection is in which we feed payload to the database this payload goes to the database as a query and in that query we put such that it creates an attack vector.
- command injection: when user input is passed to the system commands.

- preventions: 'allow list'(we compare the input sent from the user before it is fed to the server with a list that contains trusted input styles) and 'stripping input'( dangerous characters like(--,#,>) are stripped out of the input )
## A04: Insecure Design 
- this vuln is majorly caused when a product is in development phase.
- the security parameters at this time are turned off which gives an attacking window.
- Insecure design vulnerabilities happen when a system is unsafe by design, not just because of coding bugs or misconfigurations. Even perfectly written code can be insecure if the architecture, logic, or assumptions behind it are flawed.
- for example : no limits on number of wrong passwords, using old libraries and technologies.
- real life example: instagram used to send reset password through the sms and while the timer for the code is going on the attacker could brute force the code.
## A05: Security misconfigurations
- enabling unnecessary features like telnet, ssh etc.
- not using protocols like https instead of https
- not using complex passwords
## A06: vulnerable and outdated software
- as the name suggests the usage of outdated software has many flaws and vulnerabilities and not updating them may cause an attack
## A07: Identificationa and authentication failures
- when the server cant properly authenticate the user.
- poor pass management, missing MFA ,etc.
## A08: Software and data integrity failure
- inability to verify the integrity of softwre updats ,ci/cd pipelines or critical data leading to execution of untrusted code.
## A09: Security logging and monitoring failures
- 