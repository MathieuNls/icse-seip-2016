---
title: "An Efficient 2-Tier Architecture For Modern Web Development"
bibliography: config/library.bib
abstract:  zsd
author: 
- name: Mathieu Nayrolles,  Abdelwahab Hamou-Lhadj
  affiliation: SBA Lab, ECE Dept, Concordia University
  location: Montréal, QC, Canada
  email: \{mathieu.nayrolles, wahab.hamou-lhadj\}\@concordia.ca
- name: Marc Montagne, Vincent Satiat
  affiliation: Toolwatch
  location: Lausanne, Switzerland
  email: \{marc, vincent\}\@toolwatch.io
classoption: conference
keyword:
- Web Paradigm
- Web Architecture
- Two tier architecture

---

# Introduction

Modern web development is dominated by the three-tier architecture. 
In the three-tier architecture, the client (i.e, the browser) presents the user interface which has been generated according to business rules (i.e, dynamic web-page generation).
The business rules might rely on stored date (i.e, a database) [@eckerson1995three]. 
Each tier (presentation, application and data) is developed and maintained separately as interchangeable modules with well-defined interfaces.
This provides a model by which developers can create flexible and reusable applications. 
By segregating an application into tiers, developers acquire the option of modifying or adding a specific layer, instead of reworking the entire application [@hirschfeld1996three]. 
In addition to the flexibility during development and maintenance, the three-tier architecture also provides flexibility during operation.
Indeed, each tier can be scale separately to meet the demand. 
Auto-scaling such architecture (i.e, adjusting the computational power of each tier without service interruption) is a popular area of research [@Leite2010, @Mao2010, @JingJiang2013, @Fernandez2014] and business [@Prodan2009, @Zhou2010].

While the three-tier architecture is popular and provide considerable advantages for developers and maintainers both, the model has been introduced more than twenty years ago.
Despite the fact that this architecture has been refined and built upon during the last two decades, the fact remains that, it has been theorized at a time where the Internet user base was 40 millions [source], Netscape was dominating the browser market [source], Javascript [source], Java [source], Linux 1.2.0 [source] and Windows 95 were just hitting the shelves.
In recent years, we assisted to the rise of two distinct set of technologies that could, if refined, replace the application layer in a classical 3-tier architecture: (a) Javascript MVC framework and (b) NoSQL database. 
Indeed, Javascript frameworks are now able to consume APIs [Angular, Backbone, React] and construct dynamic page web and NoSQL databases provide APIs for client to consume and support the map-reduce paradigm [CouchDb]. 
In theory, one could build a CRUD (create, read, update, delete) two-tier application with a Javascript Framework and a NoSQL database.
Javascript applications are served statically to users (i.e, the pages are not dynamically generated) and then, use the Javascript engines of browser to construct html pages based on API calls to the NoSQL database.

Significant gaps exist, however, in these technologies for them to be able to remove entirely the application layer of the three-tier architecture: 
(a) read/write privileges, (b) account management and (c) schema management.

Indeed, NoSQL databases only provide privileges at the database level.
Consequently, an user with the read (write) permission is able to read (write) all the database.
Then, users have come to expect from every web-based service some kind of _reset password_ functionality even thought it provide a single point of failure into the application security (i.e. the sent email) and the NoSQL databased nor the Javascript application are able to propose such a feature.
Finally, NoSQL database are schema-less meaning that they do not have an enforceable definition of what should or should not be in the database.
If the database API were to be accessible publicly, then, any malicious user could create database entries containing unexpectedly large documents resulting in a DOS (Denial Of Service) attack.

As a result, companies using Javascript application for their presentation layer and NoSQL database for their data layer are developing and maintaining an application layer using a server-side language.  
As depicted by Figure \ref{fig:3.png}, the application layer assess if the current user is authenticated and authorized to do a given action and forwards the call to the NoSQL API.

\input{tex/3tiered}	

In order to assess these gaps, we created an add-on for a popular NoSQL database.
More specifically, when a request is made to the NoSQL database through its HTTP-API, our add-on filters out unauthorized actions and ensures that the database access are not harmful.
In addition, our add-on provides missing functionalities such as access rights, account and schema management by means of a JSON configuration file. 

In this paper, we present how we overcome these limitations and created an efficient two-tiered architecture for web services.
We experimented this new web-programming paradigm at Toolwatch; a web-based company that allows tens of thousands of clients to measure the accuracy of their mechanical watch every day, and found that operation costs can be reduced by 63% while improving performances by 34%.
In addition, the time required to develop new feature can be reduced by 41%. 

The rest of this paper is organized as follows. 
Section \ref{sec:approach} presents our approach while sections \ref{sec:exp} and \ref{sec:result} describe our case study setup and results.
Then, section \ref{sec:threats} presents the threats to validity.
Finally, sections \ref{sec:relwork} and \ref{sec:conclusion} present the related work and propose a conclusion to this paper.

# A Modern 2-Tier Architecture {#sec:approach}



# Case Study Setup {#sec:exp}

# Case Study Results {#sec:result}

# Threats to Validity {#sec:threats}

# Related Work {#sec:relwork}

# Conclusion {#sec:conclusion}



# References

