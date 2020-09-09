---
title: "Long Term Support – The Eclipse Way"
date: 2020-09-09T11:00:00-04:00
weight: 1
---

_The original article was published in [Jaxcenter](https://jaxenter.de/long-term-support-1144) and S&S Media kindly allowed us to publish the english version here._

As Open Source moves into mainstream applications, it becomes imperative that support issues in that code can be addressed throughout the lifecycle of those applications. This is often difficult as the Open Source communities tend to focus on new function and not on maintaining older releases.

_by Dr. Jutta Bindewald and Pat Huff_

 What do many commercial applications have in common with many aircraft design tools?  They are both mission-critical, they both contain open source (often Eclipse components), and they both have to be functional for many, many years.  Keeping these applications up and running over potentially long time frames is crucial and at the same time a major challenge. Changes in the environment and in data structures, not to mention the addition of new application features, may awaken bugs that have slept peacefully for years. Modifications in the upper software layers of the application may activate previously undetected problems in the lower layers. The reality is that an application may crash even after having worked just fine for a long time.

If your business is to build, sell, and run professional software, you are faced with the task of supporting your offering over its complete life-cycle. If the problem is in your own code, you may be able to analyze and fix the bug. There is know-how in your company, you own the source code, you have access to the build scripts, and the test environment, so you have a way forward.

However, what if it turns out that the problem is caused by a bug in an open source component that you used in your solution? Eclipse is well known as an open source community that produces exceptional developer tools and runtimes, that also embraces and encourages commercial adoption of their technology.  Indeed, the Eclipse Foundation is unique among the open source communities in addressing issues important to commercial adopters, such as intellectual property and legal clearance. Now, Eclipse is extending that to the support issues of its consumers. As these consumers come to depend on products built on Eclipse technology, the ability to maintain these products throughout the complete life cycle of a commercial offering becomes another important part of the value proposition to them.

**The Lifespan Problem**

Official support for a version of an Eclipse project ends after 9 months with the release of Service Release 2. If you discover a bug in an ancient (from the open source project committer perspective) version, it may either already be fixed in the current version under development at Eclipse, or you may be told that it will be fixed in the next support release or perhaps in the next major version. None of these alternatives may be adequate for your needs. Moving your product to the latest version is often not a viable option. The risk and the cost of exchanging components inside a productive solution are high, and many customers are not willing to accept that risk without seeing a clear benefit. In addition, there are often regulatory requirements for multiple years of stability which prohibit a migration to newer releases at the same rate and pace as a vibrant open source community like Eclipse. For example, aerospace companies have to ensure software maintenance of their offerings for decades.

**The Options**

So how do you fix bugs in (possibly very) old versions of Eclipse projects? There are basically two options: you do it yourself or you can look for professional help.

The do-it-yourself option has a number of challenges you must surmount. Yes, you will find the source code in the Eclipse repositories; however do you understand that code well enough to apply critical changes? Can you re-create the build and the appropriate test environment? Can you sign the binaries? There are also legal considerations. For example, the Eclipse Public License requires that you make all your source code changes publicly available.

The professional-help option is also not as easy as it sounds. You need to quickly find the right maintenance provider for your specific problem.  In the best case, you would want to choose between several providers, but how would you compare them? Once you have decided upon a maintenance provider, you have to make sure that you are not locked into that one provider; what happens to the source code, binaries, etc. if you want to switch to another provider?

**The Eclipse Answer**

This is where the Eclipse Long Term Support (LTS) Working Group comes into the picture.  The LTS Working Group was created to empower you to meet your long term maintenance requirements for Eclipse technologies that are commercially adopted in two different ways. First, should you wish to address long term support issues directly, LTS provides the infrastructure and a support-oriented community, as well as a  market that enables  you to successfully provide support for your customers over the many years of your product’s life cycle.

Second, LTS is designed to help those companies or individuals who are in the business of providing professional support and guidance for those with long-term maintenance requirements involving Eclipse componets (the “Maintenance Providers”).

Here are some of the building blocks of LTS:

·       The Marketplace  
This is where maintenance providers advertise their offerings and where a potential consumer of these services can find the professionals to help them.  

·       The Technical Infrastructure  
This shared infrastructure offers all necessary mechanisms to the maintenance providers: from source repository to signed binaries. We will describe it in more detail below.

·       The Organization  
LTS is organized as an Eclipse Working Group. Maintenance providers must join the Working Group which empowers them to leverage the LTS infrastructure and enjoy a wide range of other benefits..

#### **How Does It Work?**

If you are a potential consumer of LTS-based support services, you do not have to be a member of the LTS organization. You simply visit the LTS Marketplace to find and contact an appropriate maintenance provider. The maintenance provider will then discuss the terms, costs, and details with you.  In general, you will get the fixes as signed binaries. The source code is available as open source under the license of the original project (usually the EPL).

If you are a maintenance provider, you join the LTS organization to benefit from the shared services and infrastructure.

Let us take a closer look at this infrastructure and how a maintenance provider would use it. It consists mainly of a Git repository, a Gerrit code review system, the Maven / Tycho build infrastructure, and a Hudson server for continuous integration.

When a bug in an older version of an Eclipse project is reported, as a Maintenance Provider, you can fetch the source from the LTS Git repository. After applying the necessary source code modifications, you push the changes to Gerrit for code review, thus also triggering the rebuild of your component. If the build succeeds, you will get the first positive vote from the Hudson voter.

But this vote is not enough; other maintenance providers are asked to review your changes and give their vote. If at least one other provider accepts your changes and no one rejects them, you are done, and the source code changes can be pushed back to the central LTS repository. You can now build your component with Maven/Tycho and deliver the signed binaries to your customer.

 This is quite easy and straightforward, isn’t it? But nevertheless, some questions may come to your mind.

\-        Is Maven / Tycho mandatory to participate in LTS? No, all projects can participate in LTS, but if you use another build infrastructure than Maven / Tycho you are obliged to check in your build scripts to ensure a reproducible build

\-        Who has access to the bug fixes I made? The source code is available (usually under the EPL) as open source to anyone, thus complying with the Open Source license terms. Access to the binaries and to the signing service is limited to LTS members.

\-        How can I create “private” bug fixes that should only be available to the public after a certain point in time (e.g. security fixes)? LTS maintenance providers are granted a private Git forge. Only the provider himself has access and can grant rights to this branch. Code changes in this branch are not subject to a public Gerrit code review.

**The LTS Market Place**

As you can see, Eclipse LTS offers an easy way for maintenance providers to fix bugs in older releases. But how can they reach potential customers? An important benefit to joining LTS is the newly-created Eclipse Market Place for LTS providers, which offers an easy entry point for maintenance providers and their customers.  Here maintenance providers can offer their services on the marketplace, listing all the projects they can provide support for. If you are a potential consumer of these services, the LTS marketplace will be an ideal way to find and choose between service providers that can help you with your problems.

Go to [http://marketplace.eclipse.org/](http://marketplace.eclipse.org/) and select Long Term Support under the list of Markets to see the current list of LTS maintenance providers.

**Collaborative and Open**

Let us emphasize one aspect: Eclipse LTS is a collaborative approach based on Open Source principles. LTS members and maintenance providers work in a shared infrastructure hosted by Eclipse. Fixes in LTS and associated binaries will be available to all LTS members. In particular, that means maintenance providers can offer not only their own bug fixes to their customers but also fixes done by other maintenance providers.

From a customer point of view this minimizes the risk of vendor lock-in. If you are no longer satisfied with your maintenance provider, or they stop supporting the project, you may choose another maintenance provider. Thanks to the shared infrastructure and the collaborative approach, none of the fixes from the original provider will be lost.