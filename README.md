# chronochain
# Cronochain: Galactic timestamps that survive us.
# Cronochain – Time that survives civilization

**One-sentence pitch**  
A 256-bit hash made from the exact rotation phases of eight millisecond pulsars at a given moment.  
No servers. No humans. No trust.  
Just physics.

**Why it exists**  
GPS dies. NTP dies. Atomic clocks stop.  
Pulsars keep spinning for billions of years with nanosecond stability.  
If you can see the sky, you can verify a Cronochain proof — today, in 1,000 years, or after the next ice age.

**What you get**  
- A timestamp that cannot be back-dated (you’d have to fake the light from stars)  
- >300 bits of real physical entropy  
- Verifiable forever with a $500 radio telescope  
- Works on Earth, Mars, or a spaceship 40 AU out — same eight stars, same truth

**Current status**  
v0.9 spec – prototype in <100 lines Python – looking for astronomers, crypto builders, and people who hate fragile time.

Because when everything else is dust, the pulsars will still be ticking.
## Quickbuild
Doc Hash → [UTC t] → Pulsar Phases (8x) → SHA3-256 → Ed25519 Sig
## Next Orbit

- **Prototype It:** Fork, run the stub on a dummy doc (this README?), verify against Tempo2 ephemeris. Commit your first hash—let's chain 'em.
- **Collaborate:** Astronomers, hit me with pulsar picks. Crypto heads, EdDSA tweaks? Devs, GPS embed script? Issues/PRs open—no gatekeeping.
- **Amplify:** Share on X: "Timestamped this with neutron stars. Cronochain: because Earth time is fragile. #PulsarProof #CosmicChain" + repo link.
- **Weave Wider:** Pair with Loom for pulsar-secured routing. Time + space = unbreakable web. Repo: [loom-dns](https://github.com/Ravagedbird/loom-dns).

Pulsars spun before us. They'll spin after. This is our tick. What's your first proof?
## Why Pulsars?
### The Founding Eight (Mainnet Set)

| PSR Name      | Period (ms) | RMS Residual | Declination | Why?                          |
|---------------|-------------|--------------|-------------|-------------------------------|
| J0437−4715   | 5.757      | 110 ns      | −47°       | Brightest, closest pulsar    |
| J1713+0747   | 4.570      | 140 ns      | +07°       | PTA workhorse                 |
| J1909−3744   | 2.947      | 120 ns      | −37°       | Extremely stable              |
| J1600−3053   | 3.598      | 160 ns      | −30°       | Southern sky coverage         |
| B1937+21     | 1.558      | 100 ns      | +21°       | Original millisecond pulsar   |
| B1821−24     | 3.054      | 190 ns      | +09°       | High DM stability             |
| J0613−0200   | 3.062      | 170 ns      | −02°       | Northern coverage             |
| J1640+2224   | 3.163      | 180 ns      | +22°       | Full sky redundancy           |

Combined: ~320 bits entropy. Unforgeable.
## JSON V.01
### Timestamp Format (v0.1)

```json
{
  "version": "0.1",
  "utc": "2025-11-20T23:45:12.000Z",
  "tai_offset": 37,
  "doc_sha3_256": "a1b2c3d4e5f6...",
  "pulsars": {
    "J0437-4715": 0.8273645182736451,
    "J1713+0747": 0.3910384019283746,
    // ... phases for all eight
  },
  "signature": "ed25519: base64_sig_here"
}
## Quickbuild

- **CTA Amp:** In Next Orbit, amp the cross-link: "Sync with Loom-DNS for pulsar-secured handshakes. Eternal time meets silent routing. [loom-dns](https://github.com/Ravagedbird/loom-dns)."



                 ↓
Verify: Recompute Phases @ t → Match? True. Else: Fraud.
