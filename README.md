# selfhosteverything
This is a collection of software labelled with it's associated license all to be installed on a home device. I will be using a radxa zero 3w/3e but these should all work on almost any environment. Eventually I would like to create an installer that will unpack all the images and install on boot via a wizard or modifying the iso.

The main intention of this is to create a device that will backup important documents from your phone or pc or even physical documents and then display them in an easy and accessible format on any device of your choosing. E.g. Phone, tablet, pc, smart fridge, whatever can grab and display an ip.

The installer will be GPL licensed to encourage free distribution of the software made. I will endeavour to try and create a physical device to sell but I don't want to prevent anyone from enjoying the project themselves. The only thing I'll eventually copyright is probably a pcb the I design for everything.

The main telos for the project is to create a very user friendly backup interface for media and almost very cloud service that you use via mobile. The vision is to be able to create data security in a genuinely plug-and-play manner.

The following is a list of softwares that will be included in the installer and their reasons for being included

# The main services a user accesses in a cloud

Documents: PaperlessNGX, a paperles document filing system. This is used to create digital backups of physical letters or file things appropriately with their internal AI. Pretty useful, user friendly, included for utility.

Photographs: Immich server, a way to backup all photos and videos from your phone privately without relying on 3rd party cloud services like icloud or google photos.

Media: Jellyfin, a media organiser and server. The reason I chose jellyfin is because it is lightweight, can be customised and has a fairly simple interface that most people would be familiar with. There are also projects like jellify that are an excellent attempt to replace spotify

Storage: Nextcloud or syncthing or samba, haven't decided. But a shared documents folder that's jsut like a onedrive or google drive area for people to be able to drop files.

Security: Bitwarden, a password manager that allows you to self host your own password vault on an encrypted part of the drive. Will possibly use this in the account creation process?

Networking: Tailscale, afaik a frontend for wireguard but it is sucha fantastic piece of software that allows all of the netwrokign to take place without any static IP and all through an encrypted "home network" style connection that allows the admin to set ACLs and profiles for different users. E.g. Set a child's profile with content filters.

Search: SearXNG, a metasearch engine that scrapes multiple sites for different answers. Removes ads in searches etc.

# Possible roadmap

PiHole: I'm reluctant to use pihole because DNS issues are a pain in the ass for a semi-decent user they're real problems for a normal user though. The focus is UX so as much as I want DNS level ad-blocking I wouldn't be comfortable shipping with it unless we could guarantee some kind of "fixes itself" situation.

AI: The reason I chose to build with the Radxa zero 3w/e is because although the little quad core isn't massive there is a 1tops NPU on there to maybe get some voice commands working with whispr or some extremely light agentic models like a troubleshooting model that could locally fix the pihole with n8n?
Point being that the rk3566 is the little brother to the rk3588 and rk3588s that are way more powerful for AI if it even becomes something people want.
I don't really encourage the use of expansive LLMs I would prefer smaller scope agents anyway so I think the platform won't be an issue and we could get soem good stuff going with the RKNN LLM guys.



There are some hurdles to cross on the way:

1. Serving the "apps" even if they're simple webapps or webviewers to a phone via a local repository during setup

2. UX of creating an account for every service. That sucks. Could I use bitwarden to have the user create oen account then maybe use the ability to generate passwords via bitwarden to script that into the next step. "bitwarden will generate your passwords automatically" tick box?

3. feature creep is real and I don't want to take the functionality of any device away if someone knows what they're doign but I also don't want normal users to regularly break their install. Maybe sudo use can be hidden behind a sudo/admin account in setup. Encourage people to have user accounts and one admin account.

4. Ability to have multiple users on the same device. All of the softwares support this to some extent. We can setup each service individually but it would be cool to have a new user wizard that listed all software and users could tick boxes to select what they wanted.
