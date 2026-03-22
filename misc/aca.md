# ACA File Format
Contributor: amp64

.ACA file is a binary file created by the HD DVD authoring process. It contains information about the advanced content authoring (ACA) for a HD DVD disc.

Credit is due to [this document](https://upcommons.upc.edu/server/api/core/bitstreams/7b7a9920-02e5-46ee-8b02-52259ca803b0/content) which, while incorrect, was a good stepping stone to figuring out the correct format.

The format of the .ACA file is as follows:
- "HDDVDACA\0" (ASCII)
- UINT32: Version
- BYTE: Flags (bit 0 indicates whether the file is encrypted)
- UINT16: Number of entries
- UINT32: Size of the ACA
- BYTES[14]: Reserved (should be zero)
- For each entry:
  - UINT32: Offset of contents within the ACA file
  - UINT32: Length of contents
  - UINT32: CRC32 of contents
  - BYTE: MIME type
  - BYTE: length of name
  - BYTE[]: name
  - BYTE[32]: Reserved (should be zero)

  - **Note: all values are in big-endian format.**
