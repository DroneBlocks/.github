# Security Policy

DroneBlocks builds software that runs on real aircraft and robots used in classrooms. Security bugs in this code can affect physical safety, so we take reports seriously and appreciate the researchers who send them.
## Reporting a vulnerability

**Please do not report security issues through public GitHub issues, discussions, pull requests, or Discord/forums**

Use one of these private channels instead:

1. GitHub private vulnerability reporting (preferred): open the affected
   repository's Security tab → Report a vulnerability. This creates a
   private advisory visible only to you and the maintainers.
2. Email: `security@droneblocks.io`.

If you are unsure which repository is affected (e.g. the issue spans `dexi-os` and `dexi-droneblocks`), report it against the one you think is the root cause and mention the others, we will route it.

### What to include

- Affected repository, branch/tag.
- Affected file(s), route(s), ROS 2 topic/service, or port.
- Vulnerability type and impact.
- Step-by-step reproduction or a proof of concept, and the setup you tested on.
- Any suggested fix or mitigation.
## Supported versions

| Component                                                                                  | Supported          |
| ------------------------------------------------------------------------------------------ | ------------------ |
| DEXI-OS — latest published image                                                           | ✅                  |
| `dexi-droneblocks` GCS, ROS 2 packages (`dexi_*`), `node-red-dexi` `main` / latest release | ✅                  |
| Older images and releases                                                                  | ❌ — please upgrade |

## Scope

### In scope

- Code in repositories owned by the `DroneBlocks` GitHub organization,
  including DEXI-OS images, the GCS web app, ROS 2 packages, Node-RED nodes,
  Docker images, setup/install scripts, and simulator tooling.
- Insecure default configuration shipped by us — e.g. default credentials,
  default Wi-Fi hotspot passwords, services exposed without authentication,
  over-privileged containers.
- Issues that let a network-adjacent attacker (e.g. on the drone's hotspot)
  execute code, alter flight parameters, arm/fly the vehicle, or read user data.

### Out of scope

- Forks of upstream projects (e.g. `PX4-Autopilot`, `ardupilot`,
  `PX4-user_guide`, `PX4-gazebo-models`) — please report to the upstream
  project. Tell us too if our fork or configuration makes it worse.
- Vulnerabilities in third-party dependencies with no demonstrated impact on
  our code (please report upstream; we will pick up the patched version).
- Physical attacks that require opening the frame or flashing hardware.
- RF jamming, GPS spoofing, and other radio-layer attacks against standard
  protocols, unless our software makes them materially easier.
- Social engineering, spam, and denial-of-service by volume.

## Testing guidelines & safe harbor

We will not pursue legal action against researchers who, in good faith:

- test only against hardware and simulators **they own or are authorized to
  use**; never against someone else's drone, classroom, or network;
- DO NOT FLY a vehicle in an unsafe way while testing. Prefer the
  simulator (`dexi-sim-ftw`) or a bench setup with propellers removed;
- avoid accessing, modifying, or retaining other people's data;
- give us reasonable time to fix the issue before any public disclosure;
- comply with applicable laws, including aviation and radio regulations.

If in doubt about whether a test is acceptable, email us first.

## Security advisories

Published advisories are listed under each repository's Security → Advisories tab. We will publish advisories after the bugs have been patched and enough time has passed to provide the update.

---

*Thank you for helping keep DroneBlocks students, educators, and their aircraft safe.*
