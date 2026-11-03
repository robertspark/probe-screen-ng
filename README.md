# Probe Screen for LinuxCNC 2.8

## Info

Probe-Screen is currently being redesigned.

## History

This repo was originally a fork of <https://github.com/verser-git/probe_screen_v2> by Serguei Glavatski / Vers.by. Hopefully, this will become a community maintained probe screen for LinuxCNC. Anyone with an interest in helping out, please submit PRs or ask to join the project via a GitHub issue.

## Install

1. See "psng/install_del_from_your.hal"
   Delete (or comment out) from all .hal files lines of the form:

   ```sh
   #loadusr -W hal_manualtoolchange
   #net tool-change iocontrol.0.tool-change => hal_manualtoolchange.change
   #net tool-changed iocontrol.0.tool-changed <= hal_manualtoolchange.changed
   #net tool-number iocontrol.0.tool-prep-number => hal_manualtoolchange.number
   ```

2. See "psng/install_add_to_your.ini" Add to your .ini settings, substitute your own constants.

3. The following folders from the archive are placed in configuration folder:

   ```sh
   /python
   /psng
   ```

4. Copy .axisrc to your home ~/ folder. If you are already using .axisrc, then only add to your file contents of this .axisrc.

## Use

Set the probe in the spindle.

Move manually probe for Z about 2-10 mm above the workpiece surface,
and for XY about the position indicated by the colored dot on the appropriate button Probe Screen.

Fill parameters. Meaning of the parameters should be clear from the names and pictures (the name pop up when approaching the mouse). If you change the parameters are automatically saved in .pref .

Hit **only** the button that corresponds to the position of the probe above the workpiece. For the other buttons - you **must** move the probe to another position above the workpiece.

You do not need to expose offsets for tool "Probe", the program desired zero offsets for the current tool makes herself, and G-code works off all in relative coordinates.
In fact, you can use the application immediately after the Home.

Any of the search ends at XY moving at the desired point (or edge, or corner, or center), Z remains in the original position.

More info <https://vers.by/en/blog/useful-articles/probe-screen>
Discussion on the forum linuxcnc.org: <https://forum.linuxcnc.org/49-basic-configuration/29187-work-with-probe>

## License

   This is a plugin for LinuxCNC
   Copyright 2015 Serguei Glavatski <info@vers.by>

   This program is free software; you can redistribute it and/or modify
   it under the terms of the GNU General Public License as published by
   the Free Software Foundation; either version 2 of the License, or
   (at your option) any later version.

   This program is distributed in the hope that it will be useful,
   but WITHOUT ANY WARRANTY; without even the implied warranty of
   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
   GNU General Public License for more details.

   You should have received a copy of the GNU General Public License
   along with this program; if not, write to the Free Software
   Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.

## Repository status and workstream maintenance

Documentation review: 3 November 2026. This is repository-local status, not an upstream release or deployment acceptance.

### Purpose and function

LinuxCNC Probe Screen

### Current objective

Maintain a clearly documented local copy for authorised evaluation/development, preserving upstream attribution and distinguishing local changes from upstream capabilities.

### Progress and evidence

This is a fork of linuxcnc-probe-screen/probe-screen-ng. Existing upstream documentation and attribution are retained. Local customisation, upstream parity, build success and runtime/hardware acceptance have not been verified in this documentation review.

### Next steps and roadmap

1. Confirm the next owner-approved outcome and reconcile this default branch with the workstream's actual source, test evidence and deployed version.
2. Compare with the upstream project before updating and use an appropriate disposable/non-live test setup.
3. Keep completed/in-progress/blocked work and next actions current here. Broader feature priorities remain for the owning workstream to agree; this update does not invent a feature commitment.

### Documentation chain

Read this README first, then the existing records and source/example entry points below. Listed paths were observed on the inspected default branch; source folders are not test results.

- [docs](docs)
- [LICENSE.md](LICENSE.md)

- [Upstream repository](https://github.com/linuxcnc-probe-screen/probe-screen-ng)

### Standing instruction for every workstream

Every agent, developer or project workstream maintaining this repository must automatically keep this README current with its purpose/function, agreed objective, dated progress, blockers, roadmap/next actions and links to authoritative records. Update it when these facts materially change, at meaningful milestones and before handback, interruption or completion; do not wait for a separate owner reminder.

Read applicable project instructions, preserve concurrent work and existing attribution/licences, and distinguish source commits from deployed versions and verified results. Link requirements, design, handover, validation and recovery records when they exist rather than creating conflicting copies. If a fact is unknown, say so and identify the next verification action. Check affected links, publish authorised changes and verify the remote commit before claiming completion.

Keep credentials, private infrastructure/access routes, private datasets and confidential material out of public documentation. This instruction does not grant new access, replace project-specific authority or approve untested hardware/live operations. Retain detailed historical evidence in project records/version history rather than an ever-growing README log.
