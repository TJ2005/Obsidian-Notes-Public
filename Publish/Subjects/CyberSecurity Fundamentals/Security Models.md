---
Title: "Security Models"
Status: 
marker: 
tags: 
Date: "2025.09.16"
Time: "15:22"
---
# Security Models
- **Definition:** A **formal representation** of a security policy.
  - Describes **how subjects, objects, and access rights interact**.
- **Purpose:**
  - Allows **mathematical proof** of security properties.
  - Helps **design and verify** access control systems.
- **Examples:**
  - **Bell-LaPadula Model** (for confidentiality).
  - **Biba Model** (for integrity).
  - **Clark-Wilson Model** (for commercial integrity).

#### Bell LaPadula Model
- Applications
	- Gvmt
	- Military
- Focuses on data confidentiality
- Properties
	- No read up.
		- A subject at lower security level shalln't have access to higher level
	- No write down
		- A subject at a higher security level shall not write at a lower level to prevent read and copy execution to destroy confidentiality.
	- Strong \* Property
		- Write permission is available only on the **same level**.
	- Tranquility Principle
		- Security Levels does not change during operation
		- Security levels do not change in a way that violates the rules of a given security policy
	- **Limitation**
		- Restricted to confidentiality
		- No Policies for changing access rights
		- Low subjects can detect the existence of high objects when it is denied access.
		- Sometimes it is not sufficient to hide only the content of objects. Their existence may have to be hidden, as well.

### BIBA Model
- Focuses on Integrity
- No Read Down
	- w
- \* Integrity Axiom states that a given level of integrity must not write to any object at a higher level of integrity ( no write up )

**It has mainly 3 Rules:**

- **SIMPLE INTEGRITY RULE**: Simple Integrity Rule states that the Subject can only **Read** the files on the Same Layer of Secrecy and the Upper Layer of Secrecy but not the Lower Layer of Secrecy, due to which we call this rule as **NO READ DOWN** 
- **STAR INTEGRITY RULE**: Star Integrity Rule states that the Subject can only **Write** the files on the Same Layer of Secrecy and the Lower Layer of Secrecy but not the Upper Layer of Secrecy, due to which we call this rule as **NO WRITE-UP** 
- **STRONG STAR INTEGRITY RUL**
### Chinese Wall Model
- based on what has already been accessed
- Conflict of Interest
	- A market analyst for a financial institution providing corporate business services.
	- Example an auditor that has already audited a specific institution wants to change jobs. It is clear that they cannot join until the cooldown period for a specific amount of time has not been expired they cannot join that company that they have audited.
- Read Rule
	- Company Dataset : Objects related to one company
- Conflict of Interest:
- Write Rule

So any organization.
whatever subject, if you have entities who are trying to access the objects, then objects are nothing but your
So, now you have a process information that might be sensitive, you would have a data set that is
is all the information related to that organization, right? How does someone, some information would be for the public consumption? Say for example, the fine
the organization that is made to the publicly available, right? But that contains the some data which was generated from the sensitivity.
right and that sensitive information has been removed from that public topic because there is a sanitized output. Are you with me? Then you have conflict of interest cards that means all the companies which are in direct competition with the current subject. Here also there are two rules, read rule and write rule. The way we had a read and a write rule in the previous two models, same way here also we have a read rule and a write rule. So what does this rule say? CD is company data set, conflict of interest, right? So we say COI object and assume that each object belongs to exactly one COI, they cannot belong to multiple COI. Now how you do all objects? It would be one COI or another. COI one is in this case I am taking a banking example, banking in testing, so all the banking related. Another COI, all telecom related. Now what is the read rule says? A subject S can read an object O.
O is in the same data set as an object already accessed. So if there is a person who has read something from Airtel and is trying to read another document from the Airtel, he can read. Itna samad hai aayam? Or he is trying to read something which belongs to another COI from which S has not accessed any of the information. So if I have accessed or read Airtel, I can read from HDFC, but I cannot read it from the track. Why? Let's say there is a concern who has accessed to this. So if, as per the read rule, if he has accessed ICICI data, if he has read ICICI data, he cannot read HDFC because they are in the same COI. But he can read ONGC data, he can read Airtel data. So the first rule was...

the annual report of ICIC.
Whatever they wanted to publicly available only that information is available.
but if I can access the internal document, it will contain sensitive information that is the
So if I upgrade and I'm trying to write to an ICICI internal database
Essentially it implies if I read from
So if I do that
If I do this, if I read from this, I was trying to write here.
And from that ride, I was trying to read the from this and write it here. So that's how there was a flow of information.
So now because of this write rule, what happens is if I have read this bottom, I cannot write it here. So essentially I need to write it here.
read write operation you cannot write it
That is how you are going to prevent the catalog. Is that clear? Any space, any doubt?
Right, so sometimes what you do is you send it as information as I say, let's say
So any report would be based on all the data right that is there with the company is going to pull out that data, verify which...
which data should be made public, which data should not be made public and then it is going to prepare that. So when you remove all that sensitive information then what is also sanitized.
That object can be read, right? So suppose I am consulting ICICI that will not stop me from reading the annual report of GO or that will not stop me from reading the HDFC report although they belong to the same COI, right? Why? Because it contains an informant for a public or the categorization is it is meant for a public, right? There is no harm in reading that particular information. There is any doubt? So this is a representation of your, if you look Chinese Hall of Hall choice, initially you are meant to pre-choice what you want to access first, whether you want to access ICICI, whether you want to access, but once you have accessed one then there are rules, then there are rules which you follow that would be fine. But that was not the case when you talked about the Bell Arbeebillam or whatever. You were either categorizing one of the levels and then you were required to provide or you were granted an access, right? So here that is what we call as a first choice what you want to access. Then all other choices would be dependent on what you have accessed first. That is not the case in the VHP or Viva model. Any queries, any doubt?
wrap it like a fist
. . . . . . . .
I am going to ask you to do a new feed. I will add it to my heating. Now I will boost it for you. Okay. Yeah. Yeah. Any query you need now? Yes. Okay. I will do it in a minute. Okay. Okay. Okay. Okay. Okay. Buy a jacket. Buy a jacket. Yeah. Stylers. What do you want? What do you want? I want a jacket. A jacket. I will take it. This was proper corporate thing. This is the best. You don't need a note. Oh, you don't need a note. What do you want? I was going to on some flight or something. I was scared because there was storms going on. So I wrote a death letter. If I died, what would happen to me? And who I would leave stuff to. I got it. This is top confidence.
I was trying to get a financial dynamic. You are going to get a financial dynamic. Chinese walls here. You have already accessed the wall. And then you tell me. Have I hacked the wall? You are going to get a financial dynamic. Throw it now. I was finding it. Yeah. There was 6 minutes left. There was actually a lot of other confidential stuff. It was clear. I must have removed this note also. But it was not very good. Maybe use a light. There is 2 minutes left. Use one object to destroy the other object and throw it. What? What? Use one object to destroy the other object and destroy the other object. I don't get it. Throw the other object. Thank you. Garjari again. Garjari. Where is Garjari? Garjari. Thank you everybody.


# References


###### Information
- date: 2025.09.16
- time: 15:22