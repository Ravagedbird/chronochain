# chronochain
# Cronochain: Galactic timestamps that survive us.
# Cronochain – Time that survives civilization

**One-sentence pitch**  
A 256-bit hash made from the exact rotation phases of eight millisecond pulsars at a given moment.  
No servers. No humans. No trust.  
Just physics.
>disclaimer I have no education, just interest, if this is dumb help me fix it, you can brag later.
## **Why it exists**  
GPS dies. NTP dies. Atomic clocks stop.  
Pulsars keep spinning for billions of years with nanosecond stability.  
If you can see the sky, you can verify a Cronochain proof — today, in 1,000 years, or after the next ice age.

**What you get**  
- A timestamp that cannot be back-dated (you’d have to fake the light from stars)  
- >300 bits of real physical entropy.  
- Verifiable forever with a $500 radio telescope.  
- Works on Earth, Mars, or a spaceship 40 AU out — same eight stars, same truth.

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
## Chronochain: Pulsar Phase Computation Pipeline
 Draft Specification – Version 0.1
 Intended Status: Experimental
 1. Introduction
 This document defines the Chronochain Phase Computation Pipeline, a deterministic
 procedure for converting a UTC timestamp into a normalized fractional spin phase for
 a specified set of millisecond pulsars.
 2. Terminology
 TOA: Time of Arrival.
 Phase: A real number in [0.0, 1.0).
 Timing Model: A parameter file describing a pulsar’s spin and astrophysical properties.
 3. Input Requirements
 Implementations must accept:- UTC timestamp (ISO8601 Z format)- Pulsar timing models (TEMPO2/PINT format)- Observer position (Earth-based, planetary, or deep-space)
 4. Pipeline Overview
 UTC → TAI → TT → TDB → Barycentric TOA → Infinite Phase → Fractional Phase
 5. Detailed Pipeline
 5.1 UTC to TDB
 UTC → TAI → TT (TC = TAI + 32.184s) → TDB via planetary ephemeris.
 5.2 Barycentric Correction
 Compute solar-system barycentric arrival time including relativity corrections.
 5.3 Phase Calculation
φ∞(t) = F0·∆t + 1/2·F1·∆t² + 1/6·F2·∆t³ + φ0
 5.4 Fractional Phase
 φ = φ∞ mod 1
 6. JSON Format
 {
 "version": "0.1",
 "utc": "2025-11-21T00:14:22.000Z",
 "tai_offset": 37,
 "pulsars": { "J0437-4715": 0.8273645182736451 }
 }
 7. Security Considerations
 Phase forgery requires astrophysical spoofing. Ephemeris integrity must be ensured.
 8. References
 Hobbs et al., TEMPO2 documentation
 PINT documentation
 RFC 2119

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

- **CTA Amp:** In Next Orbit, amp the cross-link: "Sync with Loom-DNS for pulsar-secured handshakes. Eternal time meets silent routing. [loom-dns](https://github.com/Ravagedbird/loom-dns)."



                 ↓
Verify: Recompute Phases @ t → Match? True. Else: Fraud.
