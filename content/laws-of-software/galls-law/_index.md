+++
title = "Gall's Law"
date = '2026-05-13'
+++

> A complex system that works is invariably found to have evolved from a simple system that worked. A complex system designed from scratch never works and cannot be patched up to make it work. You have to start over with a working simple system.

— John Gall, *Systemantics: How Systems Work and Especially How They Fail* (1975)

# Gall's Law: From Architectural Nightmares to Evolutionary Success

Imagine you're the lead on a software project and someone insists on tearing down the existing code to build a brand-new system from scratch. After three years of work, you release it – only to see competitors overtake you and your market share collapse. That's exactly what happened to Netscape in the late 1990s. Netscape 6.0 launched years behind schedule because the team chose a "Big Bang" rewrite of their browser, which [Joel Spolsky](https://www.joelonsoftware.com/2000/04/06/things-you-should-never-do-part-i/#:~:text=Well%2C%20yes,any%20software%20company%20can%20make) later called "the single worst strategic mistake any software company can make: [to] rewrite the code from scratch". 
By the time they shipped, Microsoft had already eaten their lunch. This story is an archetypal **architectural nightmare** – wasted time, frustrated developers, and a product that barely functions.

The root cause of such disasters was summarized decades earlier by physician‐turned‐systems theorist John Gall. In his 1975 book _Systemantics_, Gall famously observed that "a complex system that works is invariably found to have evolved from a simple system that worked. A complex system designed from scratch never works and cannot be patched up to make it work. You have to start over with a working simple system." <sup>1</sup>. 
In short, any intricate software solution we think we can meticulously specify up front is almost guaranteed to fail. **Only by starting with a small, functioning core and gradually growing it can we build reliable complexity.**

Gall's Law underpins the modern push for iterative development and modularity. It explains why the World Wide Web and the blogosphere – systems that grew bit by bit from humble beginnings – succeeded where grandiose visions like CORBA (the Common Object Request Broker Architecture) failed. 
The law essentially says: **treat complexity as a badge earned by evolution, not a design goal.**

## Why Complexity Built Upfront Fails

Large, monolithic designs often suffer from hidden assumptions and untested interactions. 
When architects imagine a system "in full glory", they can't possibly foresee every data flow, user scenario, or integration issue. 
Without real feedback, the system balloons in tangled dependencies. Gall's law highlights **feedback loops and modularity** as saviors: by building a simple version first, each new feature or module can be tested in context, refined, and reassembled. 
This aligns with agile and lean principles: start simple, validate, then expand.

Conversely, when a team tries to deliver all features at once, any unknown flaw is deeply buried. 
The system's parts weren't allowed to prove themselves independently. There are no quick feedback loops. 
When a subsystem doesn't work as expected, fixing it can trigger unforeseen breakages elsewhere. In Gall's words, you will often have to "start over" with a simpler base. 
In practice, that means heavy cost: rework, wasted resources, and missed market opportunities.

## Real-World Failures: When Gall's Law Was Ignored

- **Netscape 6.0 (1999)**: Netscape's developers spent three years rewriting their browser from the ground up, leaving long-time users with an outdated version. As Joel Spolsky recounts, this was exactly the "single worst strategic mistake": a full rewrite that simply didn't work<sup>1</sup>. They effectively fell victim to Gall’s Law – the new version never reached the reliability or features of the old code base, forcing them to limp along with legacy code while competitors innovated.
- **FBI's Virtual Case File (VCF) (2002–2005)**: The FBI's effort to replace paper case files with a digital "Virtual Case File" system cost over $170 million and was ultimately abandoned <sup>2</sup>. Investigations later pointed out that FBI leadership treated this as a straightforward digital conversion, not realizing it required a profound change in work processes. They attempted a waterfall‐style redesign of the entire case-management system. By the time they uncovered its flaws, millions of lines of code had been written that simply didn't meet the real needs. The VCF project is often cited in government IT as a cautionary tale: don't attempt a colossal "big bang" transformation without iterative feedback.

In both cases, teams underestimated how tightly coupled and sensitive large systems are. Without a simple working core to iterate on, small errors amplify. As Gall noted, "we consistently fail to create large-scale systems that work as well as, say, gravity or photosynthesis" when we jump straight to ambitious designs.

### Success Stories: Growing by Evolution

Gall's law isn't just a lament; it's a prescription. Many modern systems have thrived because they evolved from modest beginnings:

- **Amazon (circa 2002–)**: Amazon famously started as an online bookstore – a simple web app with one core function (selling books). Instead of rewriting for each new business line, Jeff Bezos mandated in 2002 that all teams **expose their functionality through service APIs** <sup>3</sup>. This Bezos API Mandate forced Amazon to break its monolith into small, independently deployable services. Each team (often a “two-pizza team”) owned a specific service or subdomain (e.g. order management, recommendations, inventory), and communicated only through explicit interfaces. This is precisely the “stream-aligned” microservices model:

![Amazon service-oriented architecture diagram](/images/472b3fddd27c.png)
_Figure: In a microservices organization, each DevOps (stream-aligned) team owns one business subdomain (service). By starting with a core bookstore system and gradually adding services via APIs, Amazon was able to scale and expand (to toys, electronics, AWS, etc.) without a single colossal rewrite._

### Biography

1. [From Gall's Law to Gaul's Law](https://engineering.salesforce.com/from-galls-law-to-gaul-s-law-21bdf61924e6/)
2. [The FBI’s Dangerous Failure to Adapt to the Digital Age](https://www.lawfaremedia.org/article/the-fbi-s-dangerous-failure-to-adapt-to-the-digital-age#:~:text=New%20technologies%20often%20present%20challenges%2C,opportunity%20to%20align%20with%20that)
3. [The Bezos API Mandate: Amazon’s Manifesto For Externalization](https://nordicapis.com/the-bezos-api-mandate-amazons-manifesto-for-externalization/#:~:text=This%20simple%20practice%20opens%20up,a%20short%20window%20of%20time)
