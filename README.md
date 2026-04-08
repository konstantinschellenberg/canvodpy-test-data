<!-- Python & Package Manager -->
[![Python](https://img.shields.io/badge/python-3.14-blue.svg)](https://www.python.org/)
[![uv](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json)](https://github.com/astral-sh/uv)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-%23FE5196?logo=conventionalcommits&logoColor=white)](https://conventionalcommits.org)

<!-- Identity -->
[![canVODpy](https://img.shields.io/badge/canVODpy-test--data-2d6a4f)](https://github.com/nfb2021/canvodpy)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![CLIMERS @ TU Wien](https://img.shields.io/badge/CLIMERS-TU_Wien-006699)](https://www.tuwien.at/en/mg/geo/climers)
[![VODnet](https://img.shields.io/badge/-VODnet-2d6a4f?labelColor=555555&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA4AAAAOCAYAAAAfSC3RAAAAAXNSR0IArs4c6QAAAHhlWElmTU0AKgAAAAgABAEaAAUAAAABAAAAPgEbAAUAAAABAAAARgEoAAMAAAABAAIAAIdpAAQAAAABAAAATgAAAAAAAABIAAAAAQAAAEgAAAABAAOgAQADAAAAAQABAACgAgAEAAAAAQAAAA6gAwAEAAAAAQAAAA4AAAAAjn8NzQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAflJREFUKBWtUEtoE1EUPe+9SczHiam/aixtqi1E7aai4kK0CAVBDFZwrQs3xp2KIriYtiKuav3QRVxYKIjFVihWrCBIaaWioKidQBsxi3SwYmMmkxidYWaemYEEKUgRPHDhXu4575x3gf+NKfVD3UQ2u/Zv7wrLF8mPfV2ZH1ZCNIM7xUCAHHjyfN6wQ8mZo3vvE4Av57tzOjfd/WZpivfJSW5wkzvomnzFe2SFTyyU+iFJtCpk1eaRfOIw84TuRsN7kEkVMDzyEjPvUtga2YiDTRFM5+m+F8XYHMZuzDqaWlQf8yVMpmJ0/DUu9g6hVNQAy8au3W04NHAV85oFRulZS+LDkIjtWmcyHT6vQHYoXwrouTWKkv4LLOAHE4N4K6dxZ2AISl4DpawVDVrYcXSFZtTPGSV8IatjUVErJ+Cwbdstx3Vw8CG+pmQIHg+HUVlWo7aSp/qz9Kn3W5p5S/x4DJ8/lfGt4kAow7bmBpQ9fuQ3RUFtM4Uz61Qk/vijbpLbgtc61n05zjQ1hCvXHmB9fT3OnT8NOWfi+uxP0IJxE4S4jrXzxrffm1xlb75Aud/cEFmD9vYW6KaNUoUmCpS3BblUPNk45sR0UBM6Qzx2qd9LVnfqujGS+64puaX8olEuj4uMHHnc2dTrcFZGtCOMxv11KxP/kfEbTTzNcyb5ar0AAAAASUVORK5CYII=&logoColor=white)](https://vodnet.netlify.app)

# canVODpy — Test Data

Reference GNSS dataset for [canVODpy](https://github.com/nfb2021/canvodpy) pipeline validation and end-to-end testing. Contains real observations from **Rosalia, Austria** — DOY **2025-001** (2025-01-01), full 24-hour day.

> [!CAUTION]
> **Confidential — Pre-release Data.**
> This dataset is shared under restricted access. Distribution, redistribution, or publication of this data or any derived results is **not permitted** without explicit written authorization from the author (Nicolas F. Bader, nicolas.bader@tuwien.ac.at). Access is granted solely to individuals authorized by the author.

---

## Usage

This repository is used as the `packages/canvod-readers/tests/test_data/` submodule in canvodpy, and as the `test_data/` directory in canvodpy-demo.

**Clone for standalone use:**

```bash
# Inside canvodpy-demo
git clone https://github.com/nfb2021/canvodpy-test-data.git test_data

# Or as part of canvodpy (included automatically via submodules)
git clone --recurse-submodules https://github.com/nfb2021/canvodpy.git
```

---

## Structure

```text
test_data/
├── valid/
│   ├── rinex_v3_04/                           # RINEX v3.04 observation files
│   │   └── 01_Rosalia/
│   │       ├── 01_reference/01_GNSS/01_raw/
│   │       │   └── 25001/                     # 96 × 15-min files (rref001*.25o)
│   │       └── 02_canopy/01_GNSS/01_raw/
│   │           └── 25001/                     # 96 × 15-min files (ract001*.25o)
│   │
│   ├── rinex_v2_11/                           # RINEX v2.11 observation files (Missouri Ozark Site, Missouri, US)
│   │   └── 02_Moflux/
│   │       ├── 01_reference/
│   │       │   └── 25001/                     # 24 × 1-hour files (MOZR01CAL_R_*.rnx)
│   │       └── 02_canopy/
│   │           └── 25001/                     # 24 × 1-hour files (MOZA01CAL_R_*.rnx)
│   │
│   ├── sbf/                                   # Septentrio Binary Format files
│   │   └── 01_Rosalia/
│   │       ├── 01_reference/25001/            # 96 × 15-min files (rref001*.25_)
│   │       └── 02_canopy/25001/               # 96 × 15-min files (ract001*.25_)
│   │
│   ├── nmea/                                  # NMEA files
│   │   └── 01_Rosalia/
│   │       ├── 01_reference/25001/            # 96 × 15-min files (rref001*.251)
│   │       └── 02_canopy/25001/               # 96 × 15-min files (ract001*.251)
│   │
│   ├── rinex_v3_04_nav_data/                  # RINEX v3.04 Mixed Navigation Data
│   │   └── 01_Rosalia/
│   │       ├── 01_reference/25001/            # 96 × 15-min files (rref001*.25p)
│   │       └── 02_canopy/25001/               # 96 × 15-min files (ract001*.25p)
│   │
│   ├── broadcast_ephemerides/                 # Broadcast ephemeris data (from SBF)
│   │   └── 02_canopy/
│   │
│   ├── aux_data/                              # Precise ephemeris products
│   │   ├── 00_aux_files/
│   │   │   ├── 01_SP3/                        # COD0MGXFIN 2025-001 orbit (5 min)
│   │   │   └── 02_CLK/                        # COD0MGXFIN 2025-001 clock (30 s)
│   │   ├── 01_SP3/                            # SP3 (pipeline search path)
│   │   └── 02_CLK/                            # CLK (pipeline search path)
│   │
│   └── stores/
│       └── rosalia_rinex/                     # Icechunk store snapshot for store tests
│
├── invalid/                                   # Malformed RINEX files for parser robustness
│   ├── binary_garbage.25o
│   ├── bitflip_numeric.25o
│   ├── blank_lines_in_data.25o
│   ├── blank_observations.25o
│   ├── crlf_line_endings.25o
│   ├── duplicate_epochs.25o
│   ├── duplicate_obs_types.25o
│   ├── empty.25o
│   ├── event_epoch.25o
│   ├── extra_long_sat_line.25o
│   ├── header_only.25o
│   ├── huge_satellite_count.25o
│   ├── invalid_epoch_flag.25o
│   ├── invalid_month.25o
│   ├── invalid_satellite_id.25o
│   ├── leap_second.25o
│   ├── misaligned_observations.25o
│   ├── missing_end_of_header.25o
│   ├── missing_obs_types.25o
│   ├── mixed_valid_corrupt.25o
│   ├── multiple_end_of_header.25o
│   ├── negative_seconds.25o
│   ├── non_ascii_header.25o
│   ├── non_numeric_observations.25o
│   ├── null_bytes.25o
│   ├── obs_type_count_mismatch.25o
│   ├── reversed_epochs.25o
│   ├── satellite_count_mismatch.25o
│   ├── truncated_at_epoch_boundary.25o
│   ├── truncated_header.25o
│   ├── truncated_mid_epoch.25o
│   ├── truncated_sat_line.25o
│   ├── wrong_version_v2.25o
│   ├── wrong_version_v4.25o
│   ├── zero_position.25o
│   └── zero_satellites.25o
│
├── LICENSE
└── README.md
```

The RINEX v2.11 data in `valid/rinex_v2_11/` are from the Missouri Ozark Site in
Missouri, US, by courtesy of Christian Frankenberg and Vincent Humphrey.

---

## Receivers

| ID | Type | Station code | Formats |
|---|---|---|---|
| `reference_01` | Open-sky reference | `rref` | RINEX v3.04, SBF, NMEA |
| `canopy_01` | Below-canopy | `ract` | RINEX v3.04, SBF, NMEA |

---

## File naming

RINEX short-name convention:

```text
ract001d00.25o
└┬┘└┬┘└┬┘└┬┘└┬─┬┘
 │  │  │  │  │ └── Extension: o = observation, _ = SBF, 1 = NMEA
 │  │  │  │  └──── Year: 25 (2025)
 │  │  │  └─────── Session: 00 / 15 / 30 / 45 (minutes)
 │  │  └────────── Hour letter: a=00h … x=23h
 │  └───────────── DOY: 001
 └──────────────── Station: ract (Rosalia canopy), rref (Rosalia reference)
```

---

## Auxiliary data

COD (Center for Orbit Determination in Europe) final products, 2025-001:

| File | Product | Interval |
|---|---|---|
| `COD0MGXFIN_20250010000_01D_05M_ORB.SP3` | Multi-GNSS precise orbits | 5 min |
| `COD0MGXFIN_20250010000_01D_30S_CLK.CLK` | Precise satellite clocks | 30 s |

---

## Invalid test files

The `invalid/` directory contains 36 malformed RINEX v3 observation files, each targeting a specific parser failure mode: truncation, corruption, structural violations, encoding issues, and edge cases (leap seconds, event epochs). Used by `test_reader_invalid.py` to verify graceful error handling.

---

## Icechunk store snapshot

`valid/stores/rosalia_rinex/` is a pre-built Icechunk store containing ingested RINEX data from the Rosalia canopy receiver. Used by store-level tests that need a real repository without running the full ingest pipeline.

---

## Ignored files

The `.gitignore` excludes:

- `.DS_Store` — macOS metadata
- `*.db` — runtime SQLite caches (e.g. `gnss_satellites_cache.db`)
- `*.zarr/` — transient Zarr preprocessing caches (rebuilt each run)

---

## License

Data collected by TU Wien, Department of Geodesy and Geoinformation.
[Apache License 2.0](LICENSE)

---

## Affiliation

Collected and maintained by **Nicolas François Bader**

[Climate and Environmental Remote Sensing Research Unit (CLIMERS)](https://www.tuwien.at/en/mg/geo/climers)
Department of Geodesy and Geoinformation, TU Wien
