# The Case for Mobile Incident Response

## Goal of Incident Response
The goal of incident response is to quickly contain and mitigate an incident. It is helpful to provide a more formal definition of incident response ("IR"):

>Incident response is an organized approach to addressing and managing the aftermath of a security breach or attack (also known as an incident). The goal is to handle the situation in a way that limits damage and reduces recovery time and costs. An incident response plan includes a policy that defines, in specific terms, what constitutes an incident and provides a step-by-step process that should be followed when an incident occurs. [^1]

## Mobile Incident Response
Mobile devices have already sufficently penetrated enterprises to warrant full support in an incident response strategy. They have access to sensitive data and impact the operations of an enterprise. And, like all technolgy, they have security flaws which expose the enterprise to risk.

While most enterprises have some level of incident response plans in place, very few have developed processes and tools to respond to a mobile incident. This is a clear gap that security teams must address.

## Future of Incident Response
Over the past 3 decades, the process of incident response has matured. Bruce Schneier, a respected security technologist, wrote about evolution and future of IR in his popular [Schneier on Security](https:/
/www.schneier.com/blog/archives/2014/11/the_future_of_i.html) [^2] blog. He identified broad focuses in each decade since the 1990s starting with protection, then moving into detection and finally focused on response by the 2010s.

He reflected that in recent years, new IR products and services are being developed and implemented due to three important trends:

1. Devices and data now regularly reside outside the control of IT departments (mobile, cloud, etc.)
2. Attack and threats are far more sophisticated and effective
3. Companies continue to under-invest in protection and detection, increasing the need for response

Each of these trends are very much a reality in the mobile ecosystem and worth exploring further.

## Controling mobile devices and data
Mobile technology, by its very definition, lives outside the traditional defined IT boundries such as local networks and firewalls. This dramatically impacts the enterprises ability to control both the devices and, perhaps more importantly, the data residing on them.  

Increasing, the mobiles devices which impact an enterprise's security are neither purchased nor managed by the IT department. Some quick examples of this include:

* Employee BYOD
* Contractors
* Vendors and supply chain
* Customers

![Where can attackers find your mobile data?](../assets/where-is-your-mobile-data.png)

While the recent trend in enterprise mobile security has been to deploy management software such as MDM, EMM and similar on BYOD scenarios, this is clearly a strategy that will not scale to your vendors, supply chain and customers. 

Furthermore, there is a growing backlash from device owner regarding these management tools and their impact on privacy. In some instances, the legal teams at large enterprises are also pushing back against solutions which intercept or collect significant personal information as it becomes a liability for them. 

The trend in mobile devices and applications is clearly towards an ecosystem where the IT and security departments have very little control over the devices.

## Effectiveness of attacks and threats

As mobile devices and apps proliferate, cyber criminals and actors focused on espionage (with both intellectual property and national security objetives) are clearly following the trend. They recognize that a significant amount of data they are targeting is now present and at times more accessible to them on mobile devices. 

While early mobile attacks were farily trivial and frankly lazy, recent trends have revealved a more sophisticated and sustained effrot to thwart mobile defences. While we will explore this topic thoroughly in the [Attacking Mobile Devices](../mobile-attacks/README.md) chapter, it is helpful to provide several examples here. 

### Mobile Threats

Let's start off looking at mobile threats. This category includes vulnerabilities discovered in mobile hardware, operating systems and applications which an attacker could take advantage of. 

Educating enterprises decision makers about the risks of mobile threats and attacks is a critical first step to addressing the issues. However, mobile attack are under-reported for several reasons:

1. Due to lack of visibility, many individuals and enterprises are not aware an attack occurred
1. In server-side attacks, enterprise may be compelled to disclose the breach due to consumer protection laws however it is unlikely a targeted mobile attack would trigger such action  

For these reasons, the most effective resources available today to educate individuals and enterprises about mobile risks are identifying the threats which could expose them to compromise.

#### Android Security Threats

Android encompasses a deep intertwined ecosystem including Google/Android, OEMs, wireless carriers and app developers. In this brief overview, we will simply provide an example of a security threat in each category.  

##### Andorid Stagefright vulnerability

In September 2015, Zimprium researcher Joshua Drake ([@jduck](https://twitter.com/jduck/)) disclosed a vulnerability impacting nearly all Android devices since Android 1.5 which could allow an attached to remotely execute code on the device. The flaw was discovered in the Stagefright library, shared coded that Android devices use to process media files. By employing fuzzing techniques, it was discovered that specifically crafted media files including images, audio and video files sent to the device would crash libstagefright and provide the attacker with the ability to compromise the device.

Joshua coordinated with the Android Security team and patches were submitted to the AOSP and shared in advance with Android partners. However, the patches were not fully effective in mitigating the flaws and additional research uncovered new attack vectors. In addition, due to the complexity to deploying changes to the fragmented Android ecosystem, most users remain vulnerable to the threat.

Note: if you own or manage risk for Android devices, you can determine if the device is vulnerable to Stagefight or other know flaws by running the [VTS for Android app]. The app, developed by the NowSecure Research Team, is fully [open sourced](https://github.com/nowsecure/android-vts/) and is actively maintained.

##### Samsung keyboard vulnerability

In June 2015, NowSecure researcher Ryan Welton ([@Fuzion24](https://twitter.com/Fuzion24)) presented at [BlackHat London](https://www.blackhat.com/ldn-15/summit.html#abusing-android-apps-and-gaining-remote-code-execution) [^4] and exposed a serious flaw in over [600 million Samsung devices](https://www.nowsecure.com/keyboard-vulnerability/). [^5] Despite following a responsible and coordinated disclosure process over the course of 9 months, the flaw was ultimately misunderstood by Samsung and at the time of the disclosure, there was no patch that users or enterprises could apply. 

To make matters worse, the insecure application was signed with system privledges granting the app and thus the attacker significant access to teh device and data through remote code execution. The app could not be disabled and regular checked for updates over the network, the trigger necessary to launch the attack. Anyone attacker with a position on the network between the endpoint and the SwiftKey update server could execuate this attack.

##### Wireless carrier examples

aaa

#### App example

Adlib?

#### iOS Security Threats

Apple is incredibly effective in how they position and market the security of iOS devices. And there are indeed many excellent security features built into the platform. However, Apple developers are just as susciptiple to creating security flaws as any other developer. A key difference between Apple's approach to security and Google's approach with Android is the availability of core Android source code (via the Android Open Source Project) for community inspection. This open approach has resulted in more flaws being identified and patched at the core of Android. However, security researcher have to employ different techniques, often requiring more time and effort, when examining iOS code. Based on Apple's effective marketing and the lack on open source code for inspection, many people in the IT industry believe that Apple is more secure. However, this is clearly not the case and can be clearly shown by examining publicaly available data.

##### Apple iOS CVEs

The Common Vulnerablilty and Exposure system maintained bt MITRE was designed to provide visibility to flaws expused in IT systems. You can filter the data by vendor and operating system which provides start contrast between the number of CVEs in Apple iOS vs. Android:

-- INSERT CVE graphs for iOS and Android --

Clearly Apple developers fair no better than any other developer in writing secure code. And the closed nature of their system means far fewer eyes are available to insect and find security flaws. Arguably, Google's more open prroach has resulted in a higher velocity of both finding and patching security flaws in the Android platform. 

##### Apple's iOS 9 Security Updates

It is also revealing to examine Apple's own security page for flaws they patched in each new version. I applaud Apple and other technology companies for the transparency in posting these updates but it certainly contrasts with the security marketing Apple publishes.

In particular, in the initial iOS 9 release, Apple patched ??109?? security flaws, many of the quite serious. There is also a history of making rapid release just after a major release to patch serious security flaws found by researchers in the new update. For example, Apple has had over ??10?? pin-bypass flaws over the years ( try to locate the article about this, I think in fool.com), a visibile example that many end users quickly understand. The ability for an attacker to circumvent the lock screen on iOS devices broadly exposes the device and data to compromise and exfiltration. 

##### iPhone 4 hardware flaw

While most identified flaws occur in software (both the operating system and mobile apps), at times flaws are identified in the hardware of a device. This issues are extremely dangerious as there are generally no mitigations against these types of flaws. 

It has been quite some time since a flaw like this was found in an iPhone however it is worth pointing out an instance of this from the past. When Apple manufactured the iPhone 4, there was a flaw in the boot process that allowed an attacker to boot an unverified boot disk. This allowed any attacker with physical access to boot the device into a modified version of iOS that disabled the pass code and allowed full access to the operating system and the data on the device.

This flaw was obviosuly fixed in the next release of the iPhone but anyone using that device was at risk and have very little mitigations they could employ.

Considering the history of CVEs in iOS, the sheer amount of new code that goes into each release and the ever increasing complexity of the device and operating system, it should be clear that iOS will continue to have security flaws which, if exploited, place the individual and enterprise at risk.

### Mobile Attacks

Unlike mobile threats, mobile attacks identify actual instances of mobile threats being exploited in the wild. While these examples are less frequent, they make the strongest case for enterprises to invest in mobile security and incident response. These attacks fall broadly into these categories:

* Known malware
* Targeted attacks
* Weaponizations of mobile threats 

In the [Case Studies](../case-studies/README.md) chapter we will provide deeper examination of real world mobile attackes. However, it is useful to provide quick examples of mobile attacks in each category.

#### Mobile Malware

Mobile malware is the most common form of mobile attacks, in particualr because they are far easier to identify by examining mobile apps. While all mobile attacks are undesirable, mobile malware is the most benign of the categories listed above. We will provide an example of malware on both iOS and Android.

##### Apple iOS XCodeGhost attack

In late 2015, researchers from Palo Alto uncovered modified versions of XCode, the development environment for iOS, avaiavle on multiple websites in China. XCode is a large download and developers in China would often choose cached versions of XCode hosted in China to improve download times.

Attackers sezied this opportunity and modified XCode so that when developers complied and ultimately deployed thier applications to the App Store, malicious code was automatically included in the applications. The malicious code would exfiltrate private data from the iOS devices after the app was installed and run.

Apple identified the affected applications and immediately removed them from the App Store. They published the list of apps on their website and worked closely with the developers to ensure a new version was pushed to the App Store quickly. Some of the apps extremely popular and the full impact of the attack is likley not yet understood.

##### Android YYY Malware

So many to choose from...which one should we pick?

#### Hacking Team weaponization of mobile threats

In perhaps the most compelling example of the risk from mobile attacks, the compromise of Italian firm Hacking Team exposed a company weaponizing and selling exploits to nation states with documented human rights violations against reporters and activists. Until the time of the compromise, Hacking Team adamently denied they sould their software to any countires with documented human rights violations. However, the compromise and then expouse of 400GB of th

## Under-investing in security
The trend of companies under-investing in security is, unfortunately, a clear reality in mobile.

In an IBM sponsored study in 2015, the Ponemon Institue found that:
> Among the more than 400 organizations studied — nearly 40 percent of which were Fortune 500 companies — almost 40 percent of them aren’t scanning the code in their apps for security vulnerabilities, leaving the door wide open to the potential hacking of sensitive user, corporate and customer data. The average organization tests fewer than half of the mobile apps it builds, and a whopping 33 percent of companies never test their apps. [^7]

- Insert stats on insecure mobile apps 

This amplifies the need for mobile incident response as the technology and data is clearly distributed, generally outside the control of IT and have a large number of security and privacy flaws.

#### Footnotes
[^1]: What is incident response? Definition from WhatIs.com. Wed. Wed Nov 11 2015. <http://searchsecurity.techtarget.com/definition/incident-response>.
[^2]: The Future of Incident Response - Schneier on Security. Web. Wed Oct 21 2015. <https://www.schneier.com/blog/archives/2014/11/the_future_of_i.html>.
[^3]: 3nd footnote
[^4]: Black Hat London 2015 | Summit. Web. Wed Oct 21 2015. <https://www.blackhat.com/ldn-15/summit.html#abusing-android-apps-and-gaining-remote-code-execution>.
[^5]: NowSecure. Samsung Keyboard Security Risk Disclosed: Over 600M+ Devices Worldwide Impacted  | NowSecure. Web. Wed Oct 21 2015. <https://www.nowsecure.com/keyboard-vulnerability/>.
[^6]: aaa
[^7]: https://securityintelligence.com/mobile-insecurity/