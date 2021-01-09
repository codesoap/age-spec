* 2020-03-25: clarified that arbitrary strings can’t be empty.
* 2020-01-08: specified the generic recipient stanza format. See
  [#9][12].
* 2019-12-29: documented the key format and generation.
* 2019-12-28: clarified how ssh-ed25519 differs from X25519. See
  [discussion][11].
* 2019-12-28: switched intro and labels to age-encryption.org/v1.
  Added a label prefix to the scrypt salt. Recipients are now all
  version scoped.
* 2019-12-27: switched keys to Bech32, armor to PEM, base64 encoding to
  the standard alphabet, and ssh-rsa body columns to 64. See
  [discussion][10].
* 2019-11-27: updated the CLI to use options for recipients and
  identities, and an optional argument for the input. See [#22][9].
* 2019-11-24: specified the ASCII armored format. See [#17][8].
* 2019-10-13: made ssh-rsa body wrap at 56 columns, so it cuts along
  byte boundaries.
* 2019-10-08: changed the scrypt work factor field to log(N). See
  [#10][7].
* 2019-10-06: made the ssh-ed25519 tweak 32 bytes again, so we can use
  X25519 to apply it, and there is no need for a scalar field
  implementation anywhere.
* 2019-10-06: removed AEAD field.
* 2019-07-20: added AEAD field to the closing of the header.
* 2019-07-11: made the ssh-ed25519 tweak 64 bytes to reduce bias. (Which
  is free because the reduction doesn’t have to be constant time.)
  Pointed out at a Bar Pitti table,
  [chose to donate £50 to ProPublica][6].
* 2019-06-24: settled the important question, the pronunciation. It’s
  “g” like in “gif”.
* 2019-06-12: introduced requirement for an scrypt recipient to be the
  only one.
* 2019-06-12: added a nonce to the HKDF payload key derivation, making
  the file key reusable. (Mostly for misuse resistance.)
* 2019-06-06: added header HMAC. Via [@lasagnasec][5].
* 2019-06-06: added “Maybe in v2” section, moved PKCS#11 to it.
* 2019-05-26: rewrote the Format section in terms of RFCs. Made minor
  changes to accommodate that, most importantly now using X25519 to
  apply the ssh-ed25519 tweak scalar.
* 2019-05-26: swapped scrypt for Argon2 in the name of implementation
  ubiquity. Switched back to SHA-256 to match the scrypt core hash.
* 2019-05-26: documented that aliases can expand to multiple keys.
* 2019-05-26: included X25519 shares in derived key according to RFC
  7748, Section 6.1 by using HKDF as suggested in RFC 5869, Section 3.1.
* 2019-05-26: reintroduced public key hash for SSH keys to identify
  encrypted and hardware keys. Via private DM. (For better privacy, use
  native keys.)
* 2019-05-19: replaced egocentric GitHub link with dedicated domain
  name.
* 2019-05-19: removed public key hash from header to get recipient
  privacy like gpg’s --throw-keyid. Via private DM.
* 2019-05-19: added Ed25519 tweak and switched to SHA-512 everywhere for
  consistency. Via [kwantam][4].
* 2019-05-16: moved ~/.config/age.keys to ~/.config/age/keys.txt and
  added aliases. Via [@BenLaurie and @__agwa][3].
* 2019-05-16: added RSA-OAEP label. Via [@feministPLT][2].
* 2019-05-16: added “created” comment to generated keys. Via
  [@BenLaurie][1].

[1]: https://twitter.com/BenLaurie/status/1128960072976146433
[2]: https://twitter.com/feministPLT/status/1128972182896488449
[3]: https://twitter.com/FiloSottile/status/1129082187947663360
[4]: https://news.ycombinator.com/item?id=19955207
[5]: https://twitter.com/lasagnasec/status/1136564661376159744
[6]: https://twitter.com/FiloSottile/status/1139052687536926721
[7]: https://github.com/FiloSottile/age/issues/10
[8]: https://github.com/FiloSottile/age/issues/17
[9]: https://github.com/FiloSottile/age/issues/22
[10]: https://groups.google.com/d/msg/age-dev/UAjkvLoCr9I/l4Q1h3OPAgAJ
[11]: https://groups.google.com/forum/#!topic/age-dev/l7_QGsojQ5s
[12]: https://github.com/FiloSottile/age/issues/9
