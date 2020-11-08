---
layout: page
permalink: /due_diligence/
custom_css: longtext
title: Questions to ask when picking tools and services
sidebar_link: false
---
&nbsp;


<!-- don't forget that drafts of this file may be in .gitignore -->

A single security training cannot possibly cover all the tools and services that there are out there. Not only this, but tools and services change. New ones appear, old ones become deprecated or lose their secure reputation, and some of our favourite tools can change names and branding. Someone who would have undergone a digital security training several years ago might have been taught to use TextSecure, but times change and this tool has now been replaced by Signal.

Still - the digital security space can be difficult to navigate. As such, I've drafted a couple of questions that journalists, activists, and others could use when deciding which security tools and services to adopt. Those questions are definitely not meant to be comprehensive, but aim to start and spark discussions.


### What do people say about this product?

One of the first things we can do is a simple web search for the product or service that we are trying to use, to check what others say about it. At the same time, don't forget that many of the comments could be paid reviews, have been copywritten by marketing specialists, or could (in an extreme case) even be the result of a malware author creating fake reviews.

So in addition to a search on the open web, it's worth taking a look at places such as:
<br>

* Wired
* Ars Technica
* Hacker News (user generated submissions)
* Reddit (user generated submissions)
* Organisations you trust (Freedom of the Press, EFF, Tactical Tech, etc.)
* Twitter accounts you trust (maybe people working at the above organisations and their contacts?)
* People whom you know and trust


<p class = "infobox">
<i>A quick example</i><br><br>

A website called objective-see claims to produce high-quality security software for MacOS. But how do we know that we can trust them?

A quick search shows us that users on Hacker News are quite big fans of this software. Finding any updates on Twitter is a bit more difficult. We had to <a href = "https://twitter.com/search?q=patrickwardle&src=typed_query" target = "_blank">search</a> for Patrick Wardle, the founder of the software, in order to figure out more details. A 10 min browse shows that Patrick is pretty well known in the field, being cited by many different respected figures, as seen <a href = "https://twitter.com/MalwareJake/status/1245442270989627392" target = "_blank">here</a>, <a href = "https://twitter.com/bcrypt/status/1245472251895361536" target = "_blank">here</a> and <a href = "https://twitter.com/KimZetter/status/1214271890870587392" target="_blank">here</a>.

Note that it might take a while to figure out how infosec Twitter works, and who's influential therein.
</p>


### Have this product's claims ever been challenged in court?

Sometimes, police or other authorities can come knocking on the door of a developer or software firm, asking for details about users. Sometimes, such information has been requested by a court, which means that a developer or company that does not comply risks a fine or prison sentence.

It's worth to do a couple of web searches that look at the name of the product or service you're trying to use, along with words such as *court case* or *subpoena*.

Don't forget, though, that court cases only reveal the information that the product owners were able or unable to share at the time of the legal request. If the legal request took place some time ago, then it's possible that the tool or service underwent some major changes in the meantime, and could be collecting more or less user data than they did beforehand.

At the same time, a lack of any court cases or subpoenas does not necessarily mean that a product is insecure - it simply suggests that it has not been popular enough to have significant police interest or that such requests have been put forward in secret.

<p class = "infobox">
The Signal messenger received a court order some time ago which asked for plenty of user data. <a href = "https://www.aclu.org/blog/national-security/secrecy/new-documents-reveal-government-effort-impose-secrecy-encryption?redirect=blog/free-future/new-documents-reveal-government-effort-impose-secrecy-encryption-company" target = "_blank">They were only able to supply incredibly basic details</a>, such as when the number was registered, but couldn't provide any of the message contents or any metadata on who messaged whom. Don't forget that they would be in huge trouble had they lied to the police and court - so we can assume that their claims about not collecting any user information were trustworthy when the legal request was made.<br><br>
Something similar happened with a VPN called Private Internet Access (PIA), which was <a href = "https://www.scribd.com/doc/303226103/Fake-bomb-threat-arrest" target = "_blank">unable to provide any meaningful data for the FBI when requested</a>. Since the consequences of lying to the FBI can be pretty dire, it is safe to assume that PIA collected very little user data at the time of the request.
</p>

### What data or permissions does this product require?

Whenever we sign up to a new service, we have to give a certain amount of seems data. It might be as little as a username, or it might be much more. Whenever you sign up to a new service - especially one that feels marketed towards people interested in security or privacy, ask yourself whether or not this service is asking for more data than it really needs to deliver the product. If the service were to be broken into or sold, then your data could be leaked. The less data it holds on you, the safer you are.

Similarly, when installing a new app, either for your phone or computer, think about the permissions it requires and only give it those that are absolutely necessary. If an app requests an unreasonably large amount of permissions and cannot justify why those are necessary - avoid it.

<p class = "infobox">
Some VPN services allow for completely anonymous sign-in, even using codes instead of emails as not to associate users with any other services or accounts. Mullvad, for example, <a href = "https://mullvad.net/en/blog/2017/6/20/mullvads-account-numbers-get-longer-and-safer/" target = "_blank">uses a sixteen digit account number. </a> In some cases, a fully anonymous registration might not be practically possible. ProtonMail, for example, <a href = "https://protonmail.com/support/knowledge-base/human-verification/" target = "_blank">requires some users to verify an email or SMS code as an anti-spam measure.</a> This is much better than sites that have a real name policy or services that require login via a discrete email account.

<br><br>Whenever a site asks for data from you, think about the reasons (security, business, anti-spam) for which it might be interested in this information. If you think that the benefits or tradeoff are not worth it for you - avoid the service.

<br><br>You can apply a similar logic to apps as well. A writing app might ask for microphone access, for example if it offers a transcription or audio notes service. It might request access to your contacts for easy sharing. If it, however, fails to function without those settings, or does not document and explain why it requires those permissions, it's best to avoid the service.
</p>

### Where is the product and its developers based?

The jurisdiction in which a product, its developers, and servers are based can prove to be very important. Laws on issues such as encryption, government access to cloud data, and privacy differ from country to country. Not only this, but if the maintainers of a certain product live in a country where intelligence agencies are known to abuse their power, they could be pressured or blackmailed into inserting backdoors or accessing cloud data.

Some companies mention their jurisdiction in their marketing materials. The team behind the ProtonMail encrypted email service frequently writes about how it is based in Switzerland, arguing that the country has very strong privacy protections. Many VPN providers will also talk about their jurisdiction, arguing that it keeps them safe from governments who want to log connection data.

Whenever you think about the jurisdiction of the services you use, remember your threat model. Different governments could be a risk for different people. It's also worth asking whether or not the service is in any way lying about issues related to jurisdiction.
<br>
<p class = "infobox">
Zoom offers people the ability to transfer their data just through servers located in a specific geographical zone. Many cloud providers can also guarantee that your data will only be stored on EU-based servers (which is also a legal requirement for some organisations). <br><br>
At the same time, not all companies are completely transparent as to their jurisdiction. Telegram claims not to have any employees working in Russia, <a href = "https://theoutline.com/post/2348/what-isn-t-telegram-saying-about-its-connections-to-the-kremlin?zd=1&zi=e7irfclt" target = "_blank">though there are reports to the contrary.</a>
</p>

### Has the product been audited?

Many VPN services now undergo a process of auditing. They ask an external company to look into their operations and confirm that they are following security practices or refusing to log any data. Reputable and well-known auditing companies have lots of incentives to give a truthful account of what they found in an audit: their whole business model is based on others seeing them as trustworthy and impartial.

It's certainly good to see a VPN undergo an audit, especially if they fix any bugs or issues as recommended by the auditors. At the same time, however, an audit might be limited in its scope. It might only look at the desktop or mobile app or [at the company's servers](https://www.pcmag.com/news/what-does-a-vpn-security-audit-really-prove). Don't forget to also check the date of an audit - the VPN might have changed some of its practices in the meantime.

<p class = "infobox">
Plenty of VPNs have undergone security audits. NordVPN hired PwC in order to attest that <a href = "https://nordvpn.com/blog/nordvpn-audit/" target = "_blank">it doesn't log any customer data</a>. The results of this audit are only available to NordVPN customers, and it just looked at the company's servers and security practices. It did not attest to the safety of its app.
<br><br>
The Swedish VPN Mullvad also conducted <a href = "https://mullvad.net/en/blog/2018/9/24/read-results-security-audit-mullvad-app/" target = "_blank">an audit of its services</a>, hiring Cure53, a cybersecurity company. The <a href = "https://cure53.de/pentest-report_mullvad_v2.pdf">final audit report</a> looked at the Mullvad client software (or applications). This audit did not investigate whether or not Mullvad was capable of logging customer data.
</p>

### Is it open source?

Much software is open source - this means that its code is freely available for anyone who would like to read, study, and remix it. Many digital security trainers will also recommend that people use open source software as frequently as possible. Since the code is open, it is much less likely that the software contains malware, tracking capabilities, or backdoors and security experts can also study it in order to find and fix any potential security bugs.

Software that is open source can still contain security bugs. A particularly nasty one, called <a href = "https://en.wikipedia.org/wiki/Heartbleed" target = "_blank">Heartbleed</a>, affected an open source package called OpenSSL used by plenty of web servers around the world. At the same time, it is often easier for security researchers to find, report, and fix bugs in open source software than in products which do not share their code.

Even if you are downloading open source software, you need to keep to all the standard precautions. Only download it from the official website, an app store or package manager you trust, check its hash if possible, and keep to software that has gathered good reviews from the security community.

<p class = "infobox">
We mentioned objective-see, a website distributing security software for the Mac, above. Many people might be fearful of installing security software on their devices if they don't fully trust its author. The source code for objective-see tools <a href = "https://github.com/objective-see" target = "_blank">is available on Github,</a> so anyone with software engineering experience who doubts the author's claims about what the software does can check it out.
<br><br>
WhatsApp is a popular encrypted messaging program. Its parent company, Facebook, has implemented end-to-end encryption for all WhatsApp messages. Facebook's CEO, Mark Zuckerberg, has <a href = "https://www.washingtonpost.com/news/the-switch/wp/2018/04/10/transcript-of-mark-zuckerbergs-senate-hearing" target = "_blank">implied that WhatsApp is end-to-end encrypted</a> on a hearing <a href = "https://www.businessinsider.com/mark-zuckerberg-will-not-be-under-oath-during-senate-hearing-2018-4?IR=T" target = "_blank">where he was legally bound to tell the truth</a>. Still, Facebook has not published the source code for the app, so experts cannot independently verify its security claims or know what type of information the company is or isn't collecting on WhatsApp users.
</p>


### Does it make any misleading claims? Are there any other controversies surrounding it?

Our relationship with software and services is based on trust. If the provider of the service breaches our trust in one way or another or engages in deceptive marketing, it might suggest that they are hiding other skeletons in their closets. Always be wary of services that promise absolute security, describe their services as 100% unhackable, or refuse to own up to any of their security mistakes.

Instead, trust those who are honest about what they can and cannot provide. The way a company treats security researchers and bug reports says a huge amount about its security culture and practices. A group that tries to silence - or even worse, take legal action - against security researchers does not take security seriously. Those that welcome feedback and quickly act on bug reports are much more worthy of our praise and support.


<p class = "infobox">
I mentioned services such as Telegram above, which have been suspected of posting misleading information about where their employees are based. This is a serious breach of user trust, and users should wonder what else companies that post misleading info about themselves could be up to.
</p>



### Some best practices

Check out how [thatoneprivacy](https://thatoneprivacysite.net/) site reviews VPNs
