# Xanadu Content Gateway Protocol (XCGP)

> An open standard for sharing content across independent hypertext
> implementations in the Xanadu docuverse.

## What is this?

XCGP is a minimal protocol that enables any Xanadu-inspired system to
reference, retrieve, and verify content on any other system — regardless
of internal architecture.

It builds on the concepts and open-source release of
[Udanax Gold](https://github.com/xanadu (original C++ release, 1999))
and the vision of [Project Xanadu](https://en.wikipedia.org/wiki/Project_Xanadu)
by Ted Nelson.

## Why?

The Xanadu docuverse envisions a connected literature where every
quotation maintains its bond to the original. That vision requires
**interoperability** — content on one implementation must be
referenceable from any other.

XCGP provides that interop layer without requiring implementations to
share:
- Data structures (enfilades, CRDTs, etc.)
- Wire protocols (FeBe, WebSocket, etc.)
- Programming languages (C++, Smalltalk, Rust, Python, etc.)
- Transaction models

## How it works

An implementation conforms to XCGP v1 by providing two HTTP endpoints:

1. **`GET /.well-known/xanadu-server.json`** — tells the world who you are
2. **`GET /api/public/work/{id}`** — serves content with BLAKE3 hash verification

That's it. Any system that serves those two endpoints can join the docuverse.

## Implementations

| Implementation | Language | Status |
|---|---|---|
| [Xudanu](https://github.com/jonesd/xudanu) | Rust | Conformant (v1) |
| Udanax Gold | C++ | Pending (needs REST adapter) |
| Udanax Green | Smalltalk | Pending |
| *Your implementation* | *Any* | [Add yours](CONTRIBUTING.md) |

## Specification

The full specification is in [spec.md](spec.md).

## Relationship to Project Xanadu

XCGP is **not** affiliated with, endorsed by, or sponsored by Ted Nelson,
Project Xanadu, the Xanadu Operating Company, Autodesk Inc., or the
Udanax development team. It is an independent community effort to enable
interoperability between systems inspired by Ted Nelson's vision.

The protocol name "XCGP" and this specification are licensed under
Apache 2.0. Anyone may implement the protocol for any purpose.

## Contributing

This is a draft specification seeking community input. Issues and pull
requests are welcome.

Priority areas for feedback:
- Tumbler format compatibility with Gold/Green
- Hash algorithm (BLAKE3 vs alternatives)
- Authentication for private content
- Trail sharing format

## License

Apache 2.0 — see [LICENSE](LICENSE).
