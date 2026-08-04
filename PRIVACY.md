# Privacy

Mo-Search is a desktop application that indexes and searches files on the
Windows computer it is installed on.

## What stays local

- The index Mo-Search builds is stored on your computer.
- Indexed file content, file paths, and search queries are not uploaded to a
  Meauxsoft cloud service.
- Mo-Search does not require a Meauxsoft account to search your files.

## What you control

Mo-Search indexes the drives, folders, and file types selected in its
configuration. Locations you exclude are not indexed. You can review, change,
or rebuild the index at any time from the application.

## Network use

Mo-Search is a local application, not a cloud service. It contacts the
Meauxsoft website only for product purposes, such as checking whether a newer
release is available and opening product documentation or web pages you ask it
to open. These requests do not carry your indexed content, file paths, or
search queries.

## MoContext and AI clients

The Mo-Search installer includes [MoContext](https://github.com/Meauxsoft/mocontext),
a local MCP server that lets a compatible AI client search and read the
Mo-Search index.

MoContext is also local: it binds to `127.0.0.1` and does not upload indexed
content to a Meauxsoft cloud service. However, the AI client you connect to it
is a separate product. A cloud-backed client may transmit the search results,
file paths, snippets, or file contents it retrieves to its own model provider,
under that provider's privacy and retention terms. A fully local workflow
requires both MoContext and a client and model stack that run locally.

See the [MoContext privacy notes](https://github.com/Meauxsoft/mocontext/blob/main/PRIVACY.md)
for detail.

## Support material

Diagnostics, support reports, screenshots, and search results can contain
personal file paths and file content. Review them before attaching them to a
public GitHub issue; see [SUPPORT.md](SUPPORT.md).

Questions may be sent to
[Questions@meauxsoft.com](mailto:Questions@meauxsoft.com).
