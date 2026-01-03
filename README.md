# selfhosteverything
This is a collection of software labelled with it's associated license all to be installed on a home device. I will be using a radxa zero 3w/3e but these should all work on almost any environment. Eventually I would like to create an installer that will unpack all the images and install on boot via a wizard or modifying the iso.

The main intention of this is to create a device that will backup important documents from your phone or pc or even physical documents and then display them in an easy and accessible format on any device of your choosing. E.g. Phone, tablet, pc, smart fridge, whatever can grab and display a web page.

The installer will be GPL licensed to encourage free distribution of the software made. I will endeavour to try and create a physical device to sell but I don't want to prevent anyone from enjoying the project themselves. The only thing I'll eventually copyright is probably a PCB the I design for everything.

The main telos for the project is to create a very user friendly backup interface for media and almost very cloud service that you use via mobile. The vision is to be able to create data security in a genuinely plug-and-play manner.

The following is a list of software that will be included in the installer and their reasons for being included

# The main services a user accesses in a cloud

Documents: PaperlessNGX,[https://github.com/paperless-ngx/paperless-ngx] a paperless document filing system. This is used to create digital backups of physical letters or file things appropriately with their internal AI. Pretty useful, user friendly, included for utility. GPL-3.0
  Trilium notes, [https://github.com/TriliumNext/Trilium] a hierarchical note taking app. Just useful to have. Doesn't support multiple users by default but can be done by creating multiple instances. Doesn't sound super practical, open to a different program. AGPL-3.0

Organisation: Some kind of calendar with multiple user profiles allowing for a private calendar and a shared or family calendar. Operation could be very similar to Timetree.

Photographs: Immich server,[https://github.com/immich-app/immich] a way to backup all photos and videos from your phone privately without relying on 3rd party cloud services like iCloud or Google photos.

Media: Jellyfin,[https://github.com/jellyfin/jellyfin] a media organiser and server. The reason I chose jellyfin is because it is lightweight, can be customised and has a fairly simple interface that most people would be familiar with. GPL-2.0
  There are also projects like jellify [https://github.com/Jellify-Music/App] that are an excellent attempt to replace spotify. MIT

Storage: Nextcloud or Syncthing or Samba, haven't decided. But a shared documents folder that's just like a OneDrive or Google drive area for people to be able to drop files.

Security: BitWarden, [https://github.com/bitwarden] a password manager that allows you to self host your own password vault on an encrypted part of the drive. Will possibly use this in the account creation process? Multiple licenses including AGPL-3.0

Networking: TailScale,[https://github.com/tailscale/tailscale] AFAIK a front-end for wireguard but it is such a fantastic piece of software that allows all of the networking to take place without any static IP and all through an encrypted "home network" style connection that allows the admin to set ACLs and profiles for different users. E.g. Set a child's profile with content filters. BSD-3 
  Headscale,[https://github.com/juanfont/headscale] an open source, self-hosted implementation of the Tailscale control server. This probably changes the requirement for a static IP so it would be nice from a privacy perspective however I doubt it's practicality. BSD-3.0

Search: SearXNG,[https://github.com/searxng/searxng] a metasearch engine that scrapes multiple sites for different answers. Removes ads in searches etc.

# Possible roadmap

PiHole: [https://github.com/pi-hole/pi-hole] I'm reluctant to use pihole because DNS issues are a pain in the ass for a semi-decent user they're real problems for a normal user though. The focus is UX so as much as I want DNS level ad-blocking I wouldn't be comfortable shipping with it unless we could guarantee some kind of "fixes itself" situation. EUPL (because special EU licensing for open source stuff makes sense, this is probably going to be the reason it's not included in the suite.

AI: The reason I chose to build with the Radxa zero 3w/e is because although the little quad core isn't massive there is a 1tops NPU on there to maybe get some voice commands working with whisper [https://github.com/openai/whisper] MIT or some extremely light agentic models like a troubleshooting model that could locally fix the pihole with n8n? [https://github.com/n8n-io/n8n] Variable license

Point being that the rk3566 is the little brother to the rk3588 and rk3588s that are way more powerful for AI if it even becomes something people want.
I don't really encourage the use of expansive LLMs I would prefer smaller scope agents anyway so I think the platform won't be an issue and we could get some good stuff going with the RKNN LLM guys.



There are some hurdles to cross on the way:

1. Serving the "apps" even if they're simple webapps or webviewers to a phone via a local repository during setup

2. UX of creating an account for every service. That sucks. Could I use bitwarden to have the user create one account then maybe use the ability to generate passwords via bitwarden to script that into the next step. "bitwarden will generate your passwords automatically" tick box?

3. feature creep is real and I don't want to take the functionality of any device away if someone knows what they're doing but I also don't want normal users to regularly break their install. Maybe sudo use can be hidden behind a sudo/admin account in setup. Encourage people to have user accounts and one admin account.

4. Ability to have multiple users on the same device. All of the software supports this to some extent. We can set-up each service individually but it would be cool to have a new user wizard that listed all software and users could tick boxes to select what they wanted.
