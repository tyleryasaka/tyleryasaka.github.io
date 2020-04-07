---
layout: post
title:  "Public Checkpoints: A No-Nonsense Proposal for COVID-19 Contact Tracing"
date:   2020-04-07
---

Smartphone-based contact tracing is a solution for the current COVID-19 pandemic that many smart people are [thinking about](https://science.sciencemag.org/content/early/2020/03/30/science.abb6936.full) and [working on](https://github.com/shankari/covid-19-tracing-projects). Contact tracing is the process of finding and isolating people that have recently interacted with someone that has tested positive for an infectious disease. In other words, it is a way to stay one step ahead of disease transmission. For COVID-19, manual contact tracing is not realistic, but technology may provide the answer.

The key to contact tracing is determining who has come into close contact with who. Technology is a promising solution because of the prevalence of smartphones and the amount of data that is available. Specifically, most contact tracing solutions being considered in the US today rely on either (1) GPS location data, or (2) bluetooth data to determine physical proximity. Two prominent examples of contact tracing apps being built are MIT's [Private Kit: Safe Paths](http://safepaths.mit.edu/) (location-based) and Stanford's [COVID Watch](https://www.covid-watch.org/#) (primarily bluetooth-based).

To be clear, I support these and other efforts that are underway. But realistically, I am skeptical. The problem with all of the approaches I've seen so far is that they require a significant portion of the population to not only download an app, but also to enable the logging of information in the background (whether via GPS or bluetooth). The above-mentioned apps are privacy-oriented, so I don't think privacy is the biggest hurdle any more. My biggest concern is that a large number of people will simply not be bothered to download and enable such an app.

So what's the alternative? I have [described](https://doi.org/10.2196/18936) and [built](https://github.com/tyleryasaka/TrackCOVID) a mobile-friendly web app that performs contact tracing using QR codes to track interactions; this model is actually similar in design to several of the bluetooth-based apps being built now. My design essentially just uses QR codes instead of bluetooth. At first glance, QR codes do not seem like an advantage over bluetooth. That's where my *public checkpoints* proposal comes in.

*Public checkpoints* are simply the QR codes from my app, placed in public gathering places - think grocery stores, workplaces, restaurants that offer take-out, etc. Public checkpoints can be generated in seconds simply by visiting this url in any web browser: [TrackCOVID.net/checkpoint](https://trackcovid.net/checkpoint). This url returns a PDF with a unique checkpoint QR code every time it is visited. This PDF can be printed and placed at the entrances of public gathering places like grocery stores. The QR code on the PDF can be scanned by any modern smartphone camera, and opens directly to a confirmation page on the [web app](https://trackcovid.net/app) telling the customer that they checked in successfully. That's it. Below is an example public checkpoint PDF:

![Public Checkpoint PDF](/assets/img/checkpoint-pdf.png){: .checkpoint-pdf}

The only process needed in addition to the above process is the (anonymous) self-reporting of COVID-19 diagnoses. This can be done easily through the web app, also in a matter of seconds. Unconfirmed self-reporting is of course vulnerable to abuse, which is why I built an [admin system](https://github.com/tyleryasaka/TrackCOVID#admin-interface) which allows diagnosis *confirmation codes* to be easily generated and given to patients by authorized users. The confirmation codes are also QR codes which can be scanned by regular smartphone cameras. The web app can be used both with and without relying on confirmation codes (currently this is a user setting).

I believe the most realistic way to get the general public to participate in contact tracing at a massive scale, in a way that is respectful of data privacy, is to implement public checkpoints. By that I mean, we need all public gathering places - e.g. grocery stores - to print out these public checkpoint PDFs and place them at entrances. Employees at these places need to direct people to scan the QR codes as they enter.

There are two primary reasons I believe public checkpoints will be effective:

1. Public checkpoints are easy for everyone to use, both for store managers to generate them and for customers to scan them. Nobody needs to download or learn a new software application, and nobody needs to fill out any registration forms.
2. Participation is publicly visible. I cannot emphasize how important this is. Humans are social creatures, and apps that log bluetooth or location data in the background are in fact *too private* for the coordinated social effort that is needed. By being asked to scan a QR code in-person and in public, people will be more likely to participate, much in the same way that people are generally more polite face-to-face than when behind a wheel or a computer screen. I believe public checkpoints, placed in a large number of public places like stores and workplaces, will be the simplest and most effective way to elicit large-scale participation in contact tracing.

This proposal is not a pipe dream. The technology already exists - over the past 2 weeks I (along with friends and colleagues) [built it](https://github.com/tyleryasaka/TrackCOVID) and [described it in a peer-reviewed paper](https://doi.org/10.2196/18936). It is ready to be deployed nationwide, not in a matter of months, but in a matter of days should the demand arise.

Here's what needs to happen to make this a reality:

1. We need government authorities to step up to the plate. Something like this should, ideally, be deployed in close coordination with the CDC. It could also be deployed first on a local scale.
2. We need input from the top epidemiologists and other medical doctors and scientists.
3. We need nation-wide store chains to take initiative and volunteer to have these public checkpoints placed at their store entrances.
4. We need more innovators and engineers such as myself to make sure this system is robust, conduct thorough evaluation and testing, and make any needed changes.
5. All of these people - government officials, doctors and scientists, corporate executives, engineers, and countless others - need to collaborate and then we need to get as many public gathering places as possible to participate by agreeing to place these checkpoints at entrances. This could be made mandatory for any place that wants to be open to the public.

Smartphone-based contact tracing is within our reach. I've laid out a plan that is practical and straightforward to implement, using a web app designed with data privacy as a primary objective. I've built it and even [created a simulation model](https://github.com/tyleryasaka/TrackCOVID#network-simulation-model) that demonstrates its potential to flatten the curve. Public checkpoints are easy to use and will elicit high participation rates. I'm ready to do my part to make smartphone-based contact tracing a reality; whether that means working on my proposal or collaborating with innovators that have alternative ideas. Contact tracing can flatten the curve and save lives, and with all of the innovation we have here in America, we have no excuse not to be using technology to do it.

How to get involved or learn more:
- Check out the website: [TrackCOVID.net](https://trackcovid.net/)
- Leave your contact info in [interest form](https://docs.google.com/forms/d/e/1FAIpQLSfj8AxQ5hVYF2cvlZGv1yopOCLHn71NigqPjyFYSv6sEaQijg/viewform). I will get back to you as quickly as possible.
- Email me directly: [contact@tyleryasaka.me](mailto:contact@tyleryasaka.me)
