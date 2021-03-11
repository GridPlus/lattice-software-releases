# Lattice Firmware History

The following document contains a list of all publicly released Lattice firmware updates. Generally they contain descriptions of major features as well as changelogs of specific pull requests and commits that were added to the codebase in that version.

## v0.10.2

*Published Jan 20 2021*

This release contains a fix to prevent random tamper events in the field related to an overly sensitive tamper mesh. 

**Changelog:**

* #1870: Revision to tamper mesh config to prevent invalid triggering in v2 hardware revs.

## v0.10.1

*Published Jan 13 2021*

This release includes a fix relative to v0.10.0.

**Changelog:**

* #1860: Adds missing call to clear staged ABI definitions at ABI filesystem init. This functionally means that users had to approve preloaded definitions before, but no longer need to.

## v0.10.0

*Published Jan 12 2021*

This is a minor release which contains features, minor UI tweaks, and bug fixes.

**Larger Features:**

* Human readable Ethereum transactions via smart contract ABI definition loading and parsing
* Permissions v0: time and spending limits on simple ETH and BTC transfers

**Changelog:**

* #1738: Cleans up various build configs.
* #1739: Removes the staging config added previously based on our observation that it would not be useful.
* #1740: Fix associated build flags in some unit tests in light of the changes to the `DEBUG` compile flag.
* #1741: Fix typo in `CMakeLists.txt`.
* #1749: lvgl `#define` renames
* #1751: Update lvgl submodule
* #1754: System hook to subscribe to card manager events
* #1759: Reset sleep timer on card insertion/removal
* #1764: Import `cb0r` lib
* #1772: Add cbor print util
* #1781: Add bignum printing to cbor print util
* #1787: Allows for display of larger Ethereum `value` amounts -- this supports display of `value`s up to `UINT256_MAX`
* #1813: Permissions v0
* #1817: Wake device on signing request
* #1821: Compile flag for clone card feature
* #1822: Compile flag for update manager
* #1823: Language update to tamper screen
* #1824: Ethereum transaction data markdown using ABIs
* #1825: Compile flag for permissions v0
* #1827: Bug fixes and corrections to permissions
* #1828: Allow paired requesters to fetch addresses outside of the device's cache
* #1830: Fixes incorrect buffer size
* #1831: Adds additional warning text when card has one PIN attempt remaining
* #1833: Updates to submodules
* #1836: One more submodule update to add more keyboard characters to lvgl's special keyboard
* #1837: Bump version to v0.10.0 and updates several constants
* #1838: Fix test runner and add missing compile flag
* #1839: Blocks permissioned auto-signing of Ethereum transactions with non-zero data payloads
* #1842: Fix bug in `system_card_insertion_hook`
* #1843: Fix bug in permissions that was preventing permissioned requesters from making ETH_MSG requests
* #1846: Comment out erroneous screen drawing function for the time being. Will be fixed at a later time.
* #1849: Updates Ethereum ABI parser module to handle edge case
* #1850: Updates Ethereum ABI parser module once more to remove erroneous sanity check from previous commit

## v0.9.8

*Published Dec 4 2020*

* #1763: Add option to display `extraText` left-justified (defaults to the legacy center alignment) and also fixes bug in calculating the size of the pages when line breaks are introduced.
* #1770: Allows our Ethereum transaction parser to parse large `chainID` values, which were previously encoded as `uint8_t`s. Sidechains, testnets, and various other networks will use larger values for the `chainID`, which this PR enables.
* #1775: Fixes race condition in `wallet_task` that occurs during the card cloning process
* #1783: Fixes a nasty bug where the device times out and blanks the screen while the user is writing down their seed phrase. We should have had a block on that screen, which has been added in this PR.
* #1786: Adds more visual cues to the different lock screens (card vs system) to give users more clarity. We have had a few confused users who haven't been able to differentiate between the screens.
* #1795: Displays GCE SSH login credentials on the device info screen, even for production devices. Almost all of our user bugs/issues have arisen on the GCE side and not being able to debug those could lead to massive support issues. We have thus elected to display the information a user needs to SSH into the device on the device info screen. This also has the benefit of enticing developers to "hack" around with their device.
* #1796: Various language updates throughout the UI.
* #1798: Fixes bug introduced by me in #1795 🙈 
* #1799: More language updates to the UI
* #1800: Fixes an oversight from #1770. We were not skipping over the chainID in the `data` field in the transaction display screen and this PR fixes that.

## v0.9.6

*Published Sep 30 2020*

* Our first version 🎉
* Core Lattice firmware functionality
