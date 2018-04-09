---
title: Human Rights Considerations in Draft MARNEW Workshop Report
abbrev: marnew-hrpc
docname: draft-marnew
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
       ins: A. Andersdotter
       name: Amelia Andersdotter
       organization: ARTICLE 19
       email: amelia@article19.org

normative:

informative:

   RFC8280:
   draft-iab-marnew-report-01:


--- abstract

This draft assess the human rights considerations raised by the I.-D. IAB Workshop on Managing Radio Networks in an Encrypted World (MaRNEW) Report ([draft-iab-marnew-report-01]). It proposes changes to the draft reports, when such changes would clarify the contents from a human rights perspective, and evaluates the implications of the discussions as recorded on human rights enjoyment.

--- middle

Introduction
============

The Human Rights in Protocols Research Group welcomes the draft report from MaRNEW workshop. In particular, we welcome the efforts to continue advancing an encrypted, secure and human rights enabling environment, as well as solid assessments of the potential impacts of considered remedies to mobile network operator difficulties on the right to privacy of an individual.

In this regard, we wish to remind the drafters and the IAB of the inherent connection between privacy and freedom of expression. The right to privacy, or to one's own personhood, reinforces the freedom of expression and freedom of opinion.

Semantics
============

The following sections addresses a few semantic problems in the draft report, that were they solved the draft report would be easier to parse from both a human rights perspective, and from a business, legal or technical perspective.

[draft-iab-marnew-report-01], Abstract, para 2:

Problem: Draft text contains  value judgements on participants' presentations could be avoided.

Solution: Remove the word "honest" in relation to CDN presentations, since it may cause readers to assume that other presenters were less forthcoming.

The new paragraph would read

   The group discussed the current Internet encryption trends and
   deployment issues identified within the IETF, and the privacy needs
   of users which should be adhered.  Solutions designed around sharing
   data from the network to the endpoints and vice versa were then
   discussed as well as analysing whether the current issues experienced
   on the transport layer are also playing a role here.  Content
   providers and CDNs gave their views of delivering
   content with mobile network operators.  Finally, technical responses
   to regulation was discussed to help the regulated industries relay
   the issues of impossible to implement or bad-for-privacy technologies
   back to regulators.

[draft-iab-marnew-report-01], Section 1, Introduction:

Problem: It is unclear whether the "requirements" referred to imply regulatory requirements enforceable by government authorities, or technical requirements. Because of the nature of issues discussed during the workshop, understanding what sorts of "requirements" are being referred to is imperative.

Solution: Specify the nature of the requirements being referred to, or remove the reference to requirements.

The new Introduction would read

   Mobile networks have a set of properties which
   places a large emphasis on sophisticated bandwidth optimization.
   Encryption is increasing on the Internet which is positive for
   consumer and business privacy and security.  Many existing mobile
   bandwidth optimization solutions primarily operate on non-encrypted
   communications; this can lead to performance issues being amplified
   on mobile networks.  Encryption on networks will continue to
   increase; and with this understanding the workshop aimed to
   understand how we can solve the issues of bandwidth optimization and
   performance on radio networks in this encrypted world.

[draft-iab-marnew-report-01], Section 1.1:

Problem: The first paragraph mixes business models with technical necessities. The last paragraph in the section Understanding "Bandwidth Optimization" refers to regulatory requirements (within the meaning of government enforced requirements or legal requirements, cf above) on mobile network operators to perform traffic filtering and monitoring.

Solution: It may facilitate understanding of human rights impacts to separate technical considerations from business considerations and legal considerations. Paragraph 3 ("Many of these functions can continue...") could be put as the last paragraph, while Paragraph 1 could be split into a technical section and a business model section, followed by a legal section.


   For the purposes of this workshop, bandwidth optimization encompasses
   a variety of technical topics related to traffic engineering,
   prioritisation, optimisation and efficiency enhancements. It also encompasses
   user-related topics such as specific subscription or billing models, and may touch upon regulatory aspects or other issues relating to regulatory, within the meaning of government initiated, concerns.

   The first category of bandwidth optimization includes:

   o  Caching

   o  Prioritisation of interactive traffic over background traffic

   o  Per-user bandwidth limit
   
   The second category of bandwidth optimization may depend on either of the first category optimization strategies, but may, in particular, also encompass:

   o  Business-related topics such as content delivery arrangements with
      specific content providers.
      
   Finally, while not strictly speaking traffic management, some
   networks employ policy-based filtering (e.g., requested parental
   controls) and many networks support some form of legal interception
   functionality per applicable laws.

   Many of these functions can continue as they're performed today, even
   with more encryption.  Others are using methods which inspect parts
   of the communication that are encrypted, and these will have to be
   done differently in an encrypted Internet.

Human Rights Considerations
===========================

Upon consideration of the draft report, no implications for internationalization ([RFC8280], sec. 6.2.5), heterogeneity support ([RFC8280], sec. 6.2.8), accessibility ([RFC8280], sec. 6.2.11) or localization ([RFC8280], sec. 6.2.12) have been found. We will further suppose that issues relating to Privacy ([RFC8280], sec. 6.2.2), Anonymity ([RFC8280], sec. 6.2.9), Pseudonymity ([RFC8280], sec. 6.2.10) and Confidentiality ([RFC8280], sec. 6.2.16) have been sufficiently addressed in the draft as is.

In the below text, Security ([RFC8280], sec. 6.2.4), Integrity ([RFC8280], sec. 6.2.16) and Authenticity ([RFC8280], sec. 6.2.17) are further considered to have been addressed, or as in progress of being addressed by the specific endeavours pointed out in the report. As such, this assessment hopes to serve as a complement to remaining Human Rights Considerations Guidelines which were not addressed by the MaRNEW draft.

## Connectivity (([RFC8280], sec. 6.2.1)

It is a priori obvious that a discussion with mobile network operators would touch upon connectivity. As a general comment, the HRPC RG is not concerned that encrypted internet traffic could create topological problems in network deployment with respect to density of base stations. It is more sensible to imagine that the density of base stations is kept low by deployers to save money on infrastructure roll-out.



In the MarNEW draft report, middleboxes are brought up frequently as an example of infrastructure rendered less useful by the ubiquitous adoption of encryption. 

Security Considerations
========================

As this draft concerns a research document, there are no security considerations as described in {{RFC3552}}. This does not mean that not addressing the issues brought up in this draft will not impact the security of end-users or operators.

IANA Considerations
==========================

This document has no actions for IANA.


Acknowledgements
================


Research Group Information
==========================

The discussion list for the IRTF Human Rights Protocol Considerations working group is located at the e-mail address <hrpc@ietf.org>. Information on the group and information on how to subscribe to the list is at:
<https://www.irtf.org/mailman/listinfo/hrpc>

Archives of the list can be found at:
<https://www.irtf.org/mail-archive/web/hrpc/current/index.html>
