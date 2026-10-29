# Installation Guide

This guide outlines a cautious workflow for preparing a Kali Linux VM. Menu labels can vary slightly by VirtualBox version and host operating system.

## 1. Prepare the host

1. Check that hardware virtualization is available and enabled.
2. Install VirtualBox from its official website.
3. Download a Kali Linux image from the official Kali website.
4. Verify downloaded files using the checksums or signature instructions provided by Kali.

Official resources:
- VirtualBox: https://www.virtualbox.org/wiki/Downloads
- Kali downloads: https://www.kali.org/get-kali/

## 2. Create or import the VM

1. Open VirtualBox.
2. Import the supplied virtual appliance if using a prebuilt VM, or create a new VM using the downloaded image.
3. Allocate CPU, memory, and storage appropriate to the host machine.
4. Select a network mode intentionally; do not assume every mode provides the same isolation.
5. Start the VM and complete any initial setup prompts.

Use the official Kali and VirtualBox documentation for version-specific instructions.

## 3. Establish a baseline

After the VM starts and basic configuration is complete:

1. Confirm that the desktop and terminal open correctly.
2. Record the VM settings you selected.
3. Create a snapshot named `clean-baseline` or another descriptive name.
4. Store a screenshot of the settings with private details hidden.

## 4. Record your environment

Fill in the actual values in `LAB-NOTES.md`. Do not publish serial numbers, credentials, public IP details that you consider sensitive, or other private information.

## Completion criteria

- [ ] VM boots successfully.
- [ ] Initial configuration is documented.
- [ ] Baseline snapshot exists.
- [ ] No secrets are included in the repository.
