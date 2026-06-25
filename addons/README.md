# OfficeCorp Add-ons

Add-ons are optional extensions that OfficeCorp agents may use when a task justifies extra capability.

OfficeCorp must remain fully functional without any add-on installed. Missing, disabled, incomplete, or incompatible add-ons must never block normal OfficeCorp routing, internal skills, governance, or delivery.

Add-ons should be treated as accelerators, not dependencies:

- keep vendor content out of the repository by default;
- document local installation steps instead of copying external repositories wholesale;
- enable add-ons explicitly through configuration;
- load only the add-on skill directly relevant to the current task;
- fall back to OfficeCorp internal skills and procedures when an add-on is unavailable.

Available add-on documentation:

- [agent-skills](agent-skills/README.md)
