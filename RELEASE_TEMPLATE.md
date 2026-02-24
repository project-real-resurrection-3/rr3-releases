# RR3 Community Edition Release Template

Use this template when creating new releases.

---

## Release Title Format

```
v[VERSION] - [RELEASE_NAME]
```

**Examples:**
- `v15.0.0 - Initial Community Release`
- `v15.1.0 - Server Browser Update`
- `v15.1.1 - Bug Fixes`

---

## Tag Format

```
v[VERSION]
```

**Examples:**
- `v15.0.0`
- `v15.1.0`
- `v15.1.1`

---

## Release Notes Template

```markdown
# 🏁 RR3 Community Edition v[VERSION]

**Release Date:** [DATE]
**Version Code:** [VERSION_CODE]
**Build:** [BUILD_NUMBER]

---

## 🎉 What's New

- Feature 1
- Feature 2
- Feature 3

## 🐛 Bug Fixes

- Fix 1
- Fix 2
- Fix 3

## ⚡ Improvements

- Improvement 1
- Improvement 2
- Improvement 3

---

## 📥 Download

**APK File:** `RR3-Community-v[VERSION].apk`

**Size:** [SIZE] MB
**Min Android:** 6.0 (API 23)
**Target Android:** 14 (API 34)

---

## 🔒 Verification

**SHA-256 Checksum:**
```
[CHECKSUM_HERE]
```

**Verify with:**
```bash
sha256sum RR3-Community-v[VERSION].apk
```

---

## ⚙️ Installation

1. Download the APK
2. Enable "Install from Unknown Sources"
3. Install the APK
4. Launch and enjoy!

**Upgrading from previous version?** Just install over the old version (your progress is preserved).

---

## 🔄 OTA Updates

This version includes automatic update checking. Future updates will notify you automatically!

---

## 📝 Full Changelog

### Added
- [List new features]

### Changed
- [List changes to existing features]

### Fixed
- [List bug fixes]

### Removed
- [List removed features, if any]

---

## ⚠️ Known Issues

- [Issue 1 and workaround]
- [Issue 2 and workaround]

*Report issues at: https://github.com/project-real-resurrection-3/rr3-releases/issues*

---

## 🙏 Credits

**Contributors:**
- [@ssfdre38](https://github.com/ssfdre38) - Project Lead
- [Other contributors]

**Testers:**
- [Beta testers]

**Special Thanks:**
- RR3 Community
- Server hosts

---

## ⚖️ Legal

**Real Racing 3** is a trademark of Electronic Arts Inc.

This is an independent community project. See [LEGAL.md](https://github.com/project-real-resurrection-3/.github/blob/main/LEGAL.md) for full legal documentation.

---

🏁 **Happy Racing!** 🏁
```

---

## Release Checklist

Before publishing a release:

- [ ] Version number updated in `UpdateManager.smali`
- [ ] Version code incremented
- [ ] APK built and tested
- [ ] Changelog written
- [ ] SHA-256 checksum calculated
- [ ] APK file named correctly: `RR3-Community-v[VERSION].apk`
- [ ] Release notes reviewed
- [ ] Tag created with correct format
- [ ] Release marked as pre-release (if alpha/beta)
- [ ] Legal disclaimer included

---

## Release Channels

### Alpha (Pre-release)
- Cutting-edge features
- May have bugs
- For testers and early adopters
- Mark as "pre-release" on GitHub

### Beta (Pre-release)
- Feature-complete
- Stability testing
- For community testing
- Mark as "pre-release" on GitHub

### Stable (Latest Release)
- Production-ready
- Thoroughly tested
- For all users
- Mark as "latest release" on GitHub

---

## OTA Integration

**Important:** The OTA updater fetches from:
```
https://api.github.com/repos/project-real-resurrection-3/rr3-releases/releases/latest
```

**What this means:**
- Only the **latest non-prerelease** version is shown in OTA
- Alpha/Beta releases marked as "pre-release" won't trigger updates
- Users on older versions will see stable releases only (unless opted into beta)

**Version Detection:**
- Uses `tag_name` from GitHub API (must be `vX.Y.Z` format)
- Compares version code (integer in APK manifest)
- Shows changelog from `body` field

---

## Example Release Command

```bash
# Create a release via gh CLI
gh release create v15.0.0 \
  --repo project-real-resurrection-3/rr3-releases \
  --title "v15.0.0 - Initial Community Release" \
  --notes-file RELEASE_NOTES.md \
  RR3-Community-v15.0.0.apk
```

**For pre-release (alpha/beta):**
```bash
gh release create v15.1.0-beta \
  --repo project-real-resurrection-3/rr3-releases \
  --title "v15.1.0-beta - Server Browser Beta" \
  --notes-file RELEASE_NOTES.md \
  --prerelease \
  RR3-Community-v15.1.0-beta.apk
```

---

## File Naming Convention

**Format:** `RR3-Community-v[VERSION].apk`

**Examples:**
- `RR3-Community-v15.0.0.apk`
- `RR3-Community-v15.1.0-beta.apk`
- `RR3-Community-v15.0.1.apk`

**Why this format?**
- Clear identification
- Version visible in filename
- Easy to manage multiple versions
- Compatible with OTA updater

---

## Need Help?

Contact [@ssfdre38](https://github.com/ssfdre38) for release assistance.
