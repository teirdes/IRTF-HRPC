--- 
title: Anonymity, Human Rights and Internet Protocols
abbrev: anon
docname: draft-tenoever-hrpc-anonymity-00
category: info

ipr: trust200902
area: IRTF
workgroup: Human Rights Protocol Considerations Research Group
keyword: Internet-Draft
stand_alone: yes
pi:
  rfcedstyle: yes
  toc: yes
  tocindent: yes
  sortrefs: yes
  symrefs: yes
  strict: yes
  comments: yes
  inline: yes
  text-list-symbols: -o*+

author:
-
       ins: N. ten Oever
       name: Niels ten Oever
       organization: ARTICLE 19
       email: niels@article19.org

normative:
  
informative: 

   RFC3552:
   RFC6973:
   RFC7258:
   RFC7626:
   RFC7858:

   torproject:
     title: Tor Project - Anonymity Online
     date: 2007
     author:
        - ins: The Tor Project
     target: https://www.torproject.org/

   Pew:
     title: Anonymity, Privacy, and Security Online
     date: 2013
     author:
        - ins: L. Rainie
        - ins: S. Kiesler
        - ins: R. Kang
        - ins: M. Madden
     target: http://www.pewinternet.org/2013/09/05/anonymity-privacy-and-security-online/

   Pew2:
     title: Online Harassment
     date: 2014
     author:
        - ins: M. Duggan
     target: http://www.pewinternet.org/2014/10/22/online-harassment/

   UIDAI:
     title: The Aadhar (targeted delivery of financial and other subsidies, benefits and services) Act
     date: 2016
     author:
        - ins: Unique Identification Authority of India
     target: https://uidai.gov.in/images/the_aadhaar_act_2016.pdf

   Blanchette:
     title: Burdens of Proof - Cryptographic Culture and Evidence Law in the Age of Electronic Documents
     date: 2012
     author:
        - ins: J.F. Blanchette
     target: https://mitpress.mit.edu/books/burdens-proof

   Gurses:
     title: Multilateral Privacy Requirements - Analysis in Online Social Network Services
     date: 2010
     author:
        - ins: F.S. Gürses
     target: https://www.esat.kuleuven.be/cosic/publications/thesis-177.pdf

   CBP6059B:
     title: CBP Declaration Form 6059B
     date: 2015
     author:
        - ins: US Customs and Border Protection
     target: https://www.cbp.gov/travel/clearing-cbp/traveler-entry-form

   UNHRC2015:
     title: Anonymity, Privacy, and Security Online (A/HRC/29/32)
     date: 2015
     author:
        - ins: D. Kaye
     target: www.ohchr.org/EN/HRBodies/HRC/RegularSessions/Session29/Documents/A.HRC.29.32_AEV.doc

   AnonTerm:
     title: "A terminology for talking about privacy by data minimization: Anonymity, Unlinkability, Undetectability, Unobservability, Pseudonymity, and Identity Management"
     date: 2010
     author:
        - ins: A. Pfitzmann
        - ins: M. Hansen
     target: http://dud.inf.tu-dresden.de/literatur/Anon_Terminology_v0.34.pdf

   
--- abstract

Anonymity is less discussed topic in the IETF than for instance security {{RFC3552}} or privacy {{RFC6973}}. This can be attributed to the fact anonymity is a hard technical problem or that anonymizing user data is not of specific market interest. It remains a fact that 'most internet users would like to be anonymous online at least occasionally' {{Pew}}. 

This document aims to break down the different meanings and implications of anonymity on a mediated computer network.

--- middle


Introduction
============

Anonymity is recognised by the UN Special Rapporteur for Freedom of Expression as 'necessary for the exercise of the right to freedom of opinion and expression in the digital age' {{UNHRC2015}}, and the decreasing space for individuals to suitably hide parts of, or their entire, identity in given contexts is reflected in increasing tendencies of self-censorship {{PEN}}, decreasing willingness from consumers to uptake new services {{Eurobarometer}} {{NTIA}} 

With Internet-enabled harassment on the increase {{Pew2}} and personally identifiable information frequently being used as a vehicle for individuals' attacks on other individuals -- some fraud reference, identity theft, ddoxing, blackmail, a more thorough discussion around conceptions of identity, anonymity and individuality is necessary.

In spite of this increasing urgency, providing anonymity does not seem an integrated objective for many protocols, even though several documents have contributed to improving anonymity such as {{RFC7258}}, {{RFC7626}}, {{RFC7858}}. 

There are initiatives on the Internet to improve end users anonymity, most notably {{torproject}}, but this all relies on adding encryption in the application layer. 

This document aims to break down the different meanings and implications of anonymity on a mediated computer network and to see whether (some parts of) anonymity should be taken into consideration in protocol development.

Vocabulary Used
===============

Concepts in this draft currently strongly hinges on {{AnonTerm}}

Anonymity
: A state of an individual in which an observer or attacker cannot identify the individual within a set of other  individuals (the anonymity set). {{RFC6973}}

Entity
: An natural or legal person giving rise to items of interest (IOIs).

Linkability
: Linkability of two or more items of interest (IOIs, e.g., subjects, messages, actions, ...) from an attacker’s perspective means that within the system (comprising these and possibly other items), the attacker can sufficiently distinguish whether these IOIs are related or not. {{AnonTerm}}

Pseudonymity
: Dervided from pseudonym, a persistent or temporary identity which is not the same as the entity's given name.

Unlinkability
: Unlinkability of two or more items of interest (IOIs, e.g., subjects, messages, actions, ...) from an attacker’s perspective means that within the system (comprising these and possibly other items), the attacker cannot sufficiently distinguish whether these IOIs are related or not. {{AnonTerm}}

Undetectability
: The impossibility of being noticed or discovered

: Undetectability of an item of interest (IOI) from an attacker’s perspective means that the 
attacker cannot sufficiently distinguish whether it exists or not {{AnonTerm}}

Unobservability
: Unobservability of an item of interest (IOI) means:
  : undetectability of the IOI against all subjects uninvolved in it and 
  : anonymity of the subject(s) involved in the IOI even against the other subject(s) involved in that IOI. {{AnonTerm}}


Research Questions
==================

Premise: activity on the network has the ability for is to be anonymous or authenticated

While analyzing protocols for their impact on users anonymity, would it make sense to ask the following questions:

1. How anonymous is the end user to:
 - local network operator
 - other networks you connect to
 - your communications peer on the other end of the pipe

2. How well can they distinguish my identity from somebody else (with a similar communication) (ie linkability)

3. How does the protocol impact pseudonomity?
 - in case of long term pseudonymity
 - in case of short term pseudonymity

4. How does the protocol, in conjunction with other protocols, impact pseudonymity?

5. Could there be advice for protocol developers and implementers to improve anonimity and pseudonymity?

Literature review
=================

Concepts of identity and anonymity have been much discussed for a long period of time. How each of these concepts are construed differs within each discipline {{}}. A computer scientist might formalise a description of identity to be the prescribed number or anonymity within a system, giving rise to concepts such as anonymity sets (k-anonymity, m-anonymity), a strong distinction between identification and authentication or {{}}. But these formal descriptions of anonymity have proven to be a poor protection for anonymity in practise {{Ohm}}. A sufficiently resourced attacker can easily puzzle together a complete or partial identity from available data.

The legal concept of both identity and anonymity, by contrast, addresses both what is prescribed for a particular process (such as the amount of information required to enter into a contract {{Blanchette}}, receive public assistance {{UIDAI}}, or acquire right of passage {{CPB6059B}}) as well as the correctness of an individual's perception of themselves (see e.g. {{}}). In legal terms anonymity too may be relative to effort: IOIs can be sufficiently anonymous with respect to the effort it would take to tie an IOI to a specific entity {{}}.

We may start from a cursory division of three epochs of privacy that have been defining for the modern day conceptualisations of identity and privacy proposed by {{Gurses}}. The first of these epochs defines privacy as a right to keep secrets and to be left alone, the second epoch introduces the concept of privacy as a right to exert control and influence also over information that is known to entities beyond the person themselves, while only the third, and most recent, development construes privacy as a right to identity, and in particular a right to shape and form one's own identity.

. From this result it is clear that any discussion of anonymity much accept the malleable position of the law, which is that anonymity should be sufficiently protected in a given circumstance. 



Use Cases
=========

- multiple identities concurrently used, mixing them in operations / keeping them distinct (talking to XMPP, alias, etc)

- when you change identity, do cross stack analysis, so you have no bleedover, anonymity on a cross protocol, cross stack level

Security Considerations
========================

As this draft concerns a research document, there are no security considerations.


IANA Considerations
==========================

This document has no actions for IANA.


Research Group Information
==========================

The discussion list for the IRTF Human Rights Protocol Considerations
proposed working group is located at the e-mail address
<hrpc@ietf.org>. Information on the group and information on how to
subscribe to the list is at
<https://www.irtf.org/mailman/listinfo/hrpc>

Archives of the list can be found at:
<https://www.irtf.org/mail-archive/web/hrpc/current/index.html>

