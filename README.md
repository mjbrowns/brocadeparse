# brocadeparse
A simple tool to connect to a brocade FabricOS switch and parse its zoning configuration (aliases, zones, configurations) so they can be re-created easily on a new set of switches

## Overview

At my company, I have a lab environment with some really aging equipment.  Currently I have 4Gbit Brocade switches and I have some brand new 32Gbit switches.  Unfortunately the 4Gbit switches won't mesh with the 16Gbit switches, so the only way to transfer the zoning information is by hand.  So, I wrote this script instead.

## Syntax
```bash
brocadeparse \<switch-FQDN\> [username]
```
_username defaults to "admin" if not specified_

## Usage Notes
* It is highly recommended to get ssh keys loaded on all the switches so you don't get prompted for the passwords a bunch of times

## Example
To copy all zoning information from one switch to another, use the following, where switch1 = source switch, and switch2 = destination switch

```bash
brocadeparse switch1 | ssh admin@switch2
```
