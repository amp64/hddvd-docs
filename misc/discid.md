# DISCID.DAT File Format
Contributor: amp64

Every HD DVD disc contains a file called `DISCID.DAT` in the `ADV_OBJ` directory. This file contains a unique identifier for the disc, which is used by the HD DVD player
to identify the disc and determine that it is a valid HD DVD disc.

The format described here has been reverse engineered by using the `CreateDISCID` tool from Jumpstart, which can read and create DISCID files, as well as the inspection of files on actual HD DVDs.
The actual definition of the format is in section 6.6 of the HD DVD Specification.

The format of the DISCID file is as follows:

- "HDDVD-V_CONF"
- Guid: Disc
- Guid: Provider
- Guid: Content
- BYTE: Search (1=on, 0=off)

The file is padded to 128 bytes. 

**Note: the guids are all in big-endian format.**
