# NETWORKWALKS-JOSHUA-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP
## Project Overview

I built a virtual cybersecurity lab with VirtualBox and Kali Linux, as part of the Networkwalks Cybersecurity program (Week 1, Project Module 1). Kali is my attacking machine, and it runs on a private NAT Network so other machines can be added later.

## Step 1: Create the NAT Network (10.0.0.0/24)

I changed the existing NatNetwork in VirtualBox from 10.0.2.0/24 to 10.0.0.0/24 and kept DHCP enabled.

<img width="1353" height="691" alt="Screenshot 2026-10-29 103216" src="https://github.com/user-attachments/assets/7ee8abf9-6db8-4990-ae28-db682bf33d50" />

## Step 2: Enable clipboard and drag/drop

In the Kali VM settings (General > Features) I set Shared Clipboard and Drag-and-Drop to Bidirectional.

<img width="1365" height="719" alt="Screenshot 2026-10-29 103638" src="https://github.com/user-attachments/assets/31fc70a8-2809-4163-9195-30e8eff2bfb9" />


## Step 3: Share the Downloads folder

In Shared Folders I added my Windows Downloads folder with Auto-mount, so it appears inside Kali.

<img width="1365" height="712" alt="Screenshot 2026-10-29 104117" src="https://github.com/user-attachments/assets/320fc542-4e2a-4be9-a01b-584ca592112e" />


## Step 4: Set Kali's IP address to 10.0.0.2/24

I set a manual address on Kali with nmcli, and checked it with the ip a command.

<img width="1005" height="237" alt="Screenshot 2026-10-29 125234" src="https://github.com/user-attachments/assets/ee143bad-f00d-4249-b29a-14d80d91735f" />


## Step 5: Test the network and internet

Kali reaches the gateway (10.0.0.1), and the internet works.
<img width="686" height="264" alt="Screenshot 2026-10-29 125454" src="https://github.com/user-attachments/assets/50c8deb1-0523-4375-8864-910cec285b2c" />


## Step 6: Snapshot

I took a snapshot of the VM, so I can restore it if something breaks.

<img width="1365" height="717" alt="Screenshot 2026-10-29 105159" src="https://github.com/user-attachments/assets/ecd4271f-6c2a-486d-9a74-be1d55a129fb" />


## Problem I faced and how I fixed it

The NAT Network was on the wrong range (10.0.2.0/24). I changed the IPv4 prefix to 10.0.0.0/24. I also found that the Kali VM was in a Saved state, which locked its settings. I shut it down properly, and then I could change them.
