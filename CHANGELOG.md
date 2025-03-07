# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## 2.0.2 (2019-07-27)

### Fixed

- Deadlock on shutdown. [#106](https://github.com/passepartoutvpn/tunnelkit/issues/106)
- Stuck on SOFT_RESET. [#105](https://github.com/passepartoutvpn/tunnelkit/issues/105)
- Tunnel dies unexpectedly on macOS. [#111](https://github.com/passepartoutvpn/tunnelkit/issues/111)
- Recover from ENOBUFS. [#112](https://github.com/passepartoutvpn/tunnelkit/issues/112)

## 2.0.1 (2019-05-28)

### Fixed

- Regression in LZO subspec.

## 2.0.0 (2019-05-28)

### Changed

- Major refactoring.

## 1.7.1 (2019-05-14)

### Added

- Partially support `--redirect-gateway block-local`. [#81](https://github.com/passepartoutvpn/tunnelkit/issues/81)

### Fixed

- Authentication failure due to local options. [#95](https://github.com/passepartoutvpn/tunnelkit/issues/95)
- Customize security level (to tolerate weak certificates). [#97](https://github.com/passepartoutvpn/tunnelkit/issues/97)
- Connection stalls on server-initiated SOFT_RESET.
- Wrong configuration mutability.

## 1.7.0 (2019-04-28)

### Changed

- Do not redirect all traffic to VPN unless `--redirect-gateway` specified. [#90](https://github.com/passepartoutvpn/tunnelkit/issues/90)
- Upgrade OpenSSL to 1.1.0j.

### Fixed

- SoftEther sends an incomplete PUSH_REPLY. [#86](https://github.com/passepartoutvpn/tunnelkit/issues/86)
- Authentication/Decrypt errors with TLS wrapping. [#88](https://github.com/passepartoutvpn/tunnelkit/issues/88), [#61](https://github.com/passepartoutvpn/tunnelkit/issues/61)
- Broken DNS when no servers provided. [#84](https://github.com/passepartoutvpn/tunnelkit/issues/84)
- UDP may disconnect on high-speed upload link. [#87](https://github.com/passepartoutvpn/tunnelkit/issues/87)
- Client certificate may fail when private key in .ovpn is encrypted. [#91](https://github.com/passepartoutvpn/tunnelkit/issues/91)
- DNS is unreachable when VPN is not default gateway. [#94](https://github.com/passepartoutvpn/tunnelkit/issues/94)

## 1.6.2 (2019-04-17)

### Added

- Basic support for proxy settings (no PAC). [#74](https://github.com/passepartoutvpn/tunnelkit/issues/74)

### Changed

- Make `hostname` optional and pick `resolvedAddresses` if nil.

### Fixed

- Negotiation times out with SoftEther. [#67](https://github.com/passepartoutvpn/tunnelkit/issues/67)
- Unable to handle continuated PUSH_REPLY. [#71](https://github.com/passepartoutvpn/tunnelkit/issues/71)
- TCP requiring multiple PUSH_REQUEST. [#73](https://github.com/passepartoutvpn/tunnelkit/issues/73)
- DNS inconsistencies. [#85](https://github.com/passepartoutvpn/tunnelkit/pull/85)

## 1.6.1 (2019-04-07)

### Fixed

- Cipher/digest erroneously required by AppExtension.

## 1.6.0 (2019-04-06)

### Added

- Handle `dhcp-option DOMAIN`. [#77](https://github.com/passepartoutvpn/tunnelkit/issues/77)

### Changed

- Refactor configuration parser for reuse.

### Fixed

- Unrecognized PKCS#8 encrypted private keys. [#80](https://github.com/passepartoutvpn/tunnelkit/issues/80)
- Handle PEM with preamble. [#78](https://github.com/passepartoutvpn/tunnelkit/issues/78)

## 1.5.2 (2019-04-01)

### Added

- Optional data count report via `TunnelKitProvider.Configuration.dataCount(in:)`.

### Changed

- Upgraded to Swift 5.

### Fixed

- `checksEKU` not propagated to TunnelKitProvider.

## 1.5.1 (2019-03-25)

### Added

- Scramble endpoints via `--remote-random`. [#76](https://github.com/passepartoutvpn/tunnelkit/issues/76)
- Support for encrypted certificate private keys. [#72](https://github.com/passepartoutvpn/tunnelkit/issues/72)

### Fixed

- Send explicit exit notification if UDP. [#29](https://github.com/passepartoutvpn/tunnelkit/issues/29)
- Broken reconnection on network change (mitigated). [#75](https://github.com/passepartoutvpn/tunnelkit/issues/75)

## 1.5.0 (2019-03-20)

### Added

- Support for legacy `--comp-lzo` compression. [#69](https://github.com/passepartoutvpn/tunnelkit/pull/69)
- Support for newer `--compress lzo` option. [#70](https://github.com/passepartoutvpn/tunnelkit/pull/70)

## 1.4.3 (2019-03-18)

### Fixed

- Several reconnection issues.
- Missing EKU flag evaluation.

## 1.4.2 (2019-03-05)

### Added

- Shut down if server pushes a compressed data packet.

### Fixed

- Custom DNS servers were not applied.
- Reject `<connection>` blocks as unsupported.

## 1.4.1 (2019-02-25)

### Added

- Override DNS servers client side. [#56](https://github.com/passepartoutvpn/tunnelkit/pull/56)
- Shut down if server pushes a compression directive. [#65](https://github.com/passepartoutvpn/tunnelkit/pull/65)

### Changed

- Enable or disable EKU according to `remote-cert-tls server` in .ovpn file. [#64](https://github.com/passepartoutvpn/tunnelkit/pull/64)

### Fixed

- Compiling errors in demo target.
- Linking errors with OpenSSL.
- A few potential vulnerabilities.

## 1.4.0 (2018-11-12)

### Added

- Parser for .ovpn configuration files. [#47](https://github.com/passepartoutvpn/tunnelkit/pull/47)

### Changed

- Due to [#47](https://github.com/passepartoutvpn/tunnelkit/pull/47), `SocketType` and `EndpointProtocol` were moved to Core subspec.

## 1.3.1 (2018-11-07)

### Fixed

- IPv4/UInt32 conversions are not endianness-agnostic. [#46](https://github.com/passepartoutvpn/tunnelkit/pull/46)

## 1.3.0 (2018-10-28)

### Changed

- Refactored tunnel configuration API for increased code reuse. [#44](https://github.com/passepartoutvpn/tunnelkit/pull/44)

### Deprecated

- Use high-level accessories instead of `debugLogKey` and `lastErrorKey`. [#45](https://github.com/passepartoutvpn/tunnelkit/pull/45)

### Fixed

- IPv4/UInt32 calculations were wrong.

## 1.2.2 (2018-10-25)

### Changed

- Debug log is saved to group container rather than `UserDefaults`. [#43](https://github.com/passepartoutvpn/tunnelkit/pull/43)

### Fixed

- Handle server-initiated renegotiation. [#41](https://github.com/passepartoutvpn/tunnelkit/pull/41)
- Potentially private data (e.g. Internet addresses) is now masked in debug log. [#42](https://github.com/passepartoutvpn/tunnelkit/pull/42)

## 1.2.1 (2018-10-24)

### Added

- Configuration key `lastErrorKey` for reporting errors to host app. [#40](https://github.com/passepartoutvpn/tunnelkit/pull/40)
- Server extended key usage validation (EKU). [#27](https://github.com/passepartoutvpn/tunnelkit/issues/27)

### Fixed

- CA file was not closed after MD5 calculation when using PIA patches.
- Mitigated an issue with MTU in TCP mode during negotiation. [#39](https://github.com/passepartoutvpn/tunnelkit/issues/39)

## 1.2.0 (2018-10-20)

### Added

- Support for `--tls-auth` wrapping. [#34](https://github.com/passepartoutvpn/tunnelkit/pull/34)
- Support for `--tls-crypt` wrapping. [#35](https://github.com/passepartoutvpn/tunnelkit/pull/35)
- Parser for static OpenVPN keys from file. [#36](https://github.com/passepartoutvpn/tunnelkit/pull/36)

### Fixed

- Handling of mixed DATA_V1/DATA_V2 packets. [#30](https://github.com/passepartoutvpn/tunnelkit/issues/30)

## 1.1.2 (2018-10-18)

### Added

- Restored support for PIA patches. [#32](https://github.com/passepartoutvpn/tunnelkit/pull/32)

## 1.1.1 (2018-10-10)

### Fixed

- Make CA non-optional. [#28](https://github.com/passepartoutvpn/tunnelkit/pull/28)

## 1.1.0 (2018-09-26)

### Added

- Client certificate verification. [#3](https://github.com/passepartoutvpn/tunnelkit/pull/3)
- Support for both `--comp-lzo` and `--compress` compression framing. [#2](https://github.com/passepartoutvpn/tunnelkit/pull/2), [#5](https://github.com/passepartoutvpn/tunnelkit/pull/5), [#10](https://github.com/passepartoutvpn/tunnelkit/pull/10)
- Routes setup from PUSH_REPLY. [#7](https://github.com/passepartoutvpn/tunnelkit/pull/7)
- Support for IPv6. [#8](https://github.com/passepartoutvpn/tunnelkit/pull/8)
- Support for server-side NCP. [#11](https://github.com/passepartoutvpn/tunnelkit/pull/11)
- Property to mark ciphers not requiring digest auth (e.g. GCM). [#13](https://github.com/passepartoutvpn/tunnelkit/pull/13)
- `Codable` implementations for native Swift serialization. [#15](https://github.com/passepartoutvpn/tunnelkit/pull/15)
- More cipher and digest algorithms. [#16](https://github.com/passepartoutvpn/tunnelkit/pull/16)
- Negotiated compression framing from PUSH_REPLY. [#19](https://github.com/passepartoutvpn/tunnelkit/pull/19)
- Customizable keep-alive. [#20](https://github.com/passepartoutvpn/tunnelkit/pull/20)
- Negotiated keep-alive from PUSH_REPLY. [#22](https://github.com/passepartoutvpn/tunnelkit/pull/22)
- Peer-info metadata.

### Changed

- Raised iOS target to 11 (drops 32-bit support).
- Upgraded OpenSSL from 1.1.0h to 1.1.0i.
- Minor adjustments for Xcode 10 / Swift 4.2.
- Deep refactoring of control channel for future extensibility.
- App group moved out of tunnel configuration, to make it more platform-agnostic and coherent to serialize.
- Keep-alive is disabled by default.
- Several internal renamings.

### Fixed

- Sensitive data logged in PUSH_REPLY. [#12](https://github.com/passepartoutvpn/tunnelkit/pull/12)
- Bad interpretation of 0 seconds between renegotiations. [#18](https://github.com/passepartoutvpn/tunnelkit/pull/18)
- Incorrect behavior on data-related failures. [#21](https://github.com/passepartoutvpn/tunnelkit/pull/21)

## 1.0.0 (2018-08-23)

### Added

- Initial fork from https://github.com/pia-foss/tunnel-apple

### Removed

- Non-standard PIA patches.
