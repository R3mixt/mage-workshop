# Mage Workshop — WoW Forever

A self-contained mage talent calculator and balance proposal editor. Open `index.html` in a browser. No installation, build step, account, or server is needed.

## Publish on GitHub Pages

1. Create a repository such as `forever-mage-talents` on GitHub. A public repository works with GitHub Free.
2. Upload `index.html` to the repository root. You can also upload this README, `.nojekyll`, and the baseline JSON for reference.
3. In **Settings → Pages**, choose **Deploy from a branch**, then **main** and **/(root)**. Save.
4. GitHub provides a URL such as `https://YOUR-USERNAME.github.io/forever-mage-talents/`. Publication may take several minutes.

Official instructions: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

Only `index.html` is required at runtime. It embeds all data, CSS, JavaScript, 67 unique icons, and three tree backgrounds. There are no CDN dependencies, analytics, or network requests during calculator use.

## Use the calculator

- **Current beta** starts with the unchanged mage trees: Arcane (18 talents), Fire (17), and Frost (19).
- First click selects a talent and shows its tooltip. Additional clicks on the same talent add points directly. Right-click or Shift-click removes a point. Hover or keyboard focus previews the tooltip; Space opens details, Enter follows the click behavior, and minus or Backspace removes a point.
- On phones and narrow screens, the first tap opens details and subsequent taps on the same talent add points. The icon stays above the detail panel. Add/Remove buttons remain available as alternatives.
- The calculator enforces level 10–60 budgets, 5-point row gates, rank caps, and maxed prerequisites. It rejects refunds that would invalidate dependent talents.
- **Talent names** adds labels. **Presentation view** hides introductory and publishing controls for screenshots or streams.

## Make balance proposals without coding

1. Select **My proposal**, then **Edit talents**.
2. Select a talent. Edit its name, maximum ranks (1–5), each rank's full text, mana/cast/cooldown text, grid location, prerequisite, and rationale.
3. Choose an empty grid position within the talent's current tree. To swap occupied talents, first move one to an empty slot. Prerequisites must be in an earlier row of the same tree.
4. Apply changes. If the new rules invalidate allocated ranks, those points are refunded. **Current beta** always preserves the original talent definitions and its separate build.
5. Turn editing off to test your proposed build. Review the before/after descriptions below the trees.
6. Add a proposal title and overall design notes. **Copy Reddit summary** produces a Markdown explanation; it does not post anything.

The editor changes or removes mage talents and can change active/passive types. This version also includes the new Burn Notice and Ice Walk talents. The UI does not create arbitrary new talent slots, move talents between trees, simulate damage, or change the game itself. Removed talents remain in the comparison list so you can review and edit their removal. A dependent talent whose prerequisite was removed is unavailable until that prerequisite is revised.

## Current proposal

The page opens in **My proposal**. **Current beta** retains all 54 original talents. The proposed tree has 54 visible talents: Lingering Frost and the old third-row Ice Lance are removed, and Burn Notice and Ice Walk are added.

- **Fire row 3, left to right:** Burn Notice, Improved Flamestrike, Pyroblast, Burning Soul. Burn Notice is a 1-rank passive and requires **5/5 Ignite**, shown by an arrow. Burning Soul stays on the same tier and retains its effect.
- **Burn Notice:** Reapplying one of your Fire damage over time effects adds its remaining damage to the new application and refreshes the duration. Pools are tracked per caster and per effect. Different Fire effects remain separate. No extra damage multiplier is granted; stack limits, tick timing and cross-Mage pooling remain open tuning decisions.
- **Flame Throwing** moves to row 4, column 2 (15 earlier Fire points required). **Improved Fire Ward** moves to row 2, column 2 (5 earlier Fire points required). Their effects and ranks are unchanged. Fully taking Flame Throwing together with 3/3 Arcane Reach now requires at least 35 talent points (17 in Fire and 18 in Arcane).
- **Lingering Frost:** Removed. Ice Walk remains available without the frost-trail speed bonus.
- **Improved Frost Ward:** Two-rank passive talent replacing Frost Warding. Adds retaliation to the existing Frost Ward spell: **9/18, 11/22, 13/26, 16/32, or 22/44 base Frost damage** for spell ranks 1–5, respectively, plus **10%/20% of bonus Frost spell damage** at talent rank 1/2. General spell damage that applies to Frost counts. Coefficients are initial proposal tuning. Physical melee/ranged attacks trigger it; periodic damage does not. Retaliation ends when the ward expires, is dispelled, cancelled or depleted. Frost Ward retains its original absorption, mana costs, instant cast, 30 sec duration and 30 sec cooldown. No benefit before learning Frost Ward at level 22. Base damage is benchmarked to level-appropriate Forever Thorns, doubled at talent rank 2 ([reference](https://wowforevertalents.com/abilities/druid/)).
- **Ice Block** becomes a baseline Mage spell learned at **level 25**, matching the original talent's earliest availability. It provides **3 sec** of immunity, costs 15 Mana, has a 10 min cooldown, and provides no healing without the talent.
- **Improved Ice Block:** Adds **7 sec** of immunity (10 sec total), reduces the cooldown by 5 min (5 min total), and heals for **30% of maximum health** over the full duration. Healing ends if Ice Block ends early.
- **Ice Lance:** Remains a 1-rank talent in the former Winter's Chill slot. It can be cast with **0–5 stacks** and clears them all. Damage is based on stacks before the cast. Frost spells grant 1 stack, non-Frost spells remove 1, and Ice Lance leaves no stacks behind.
- **Arcane Resilience:** Replaces Arcane Shielding and swaps positions with Arcane Reach: row 3, column 1 (10 earlier Arcane points required). Its two ranks reduce the duration and effectiveness of debuffs on you by **15%/25%**. Magical Precision remains in the earlier slot.
- **Arcane Reach:** Moves to row 4, column 1 (15 earlier Arcane points required). Its three ranks still increase the range of all spells by 3/6/9 yards.
- **Mana Shield:** All ranks gain the former full **33%** mana-drain reduction as a baseline benefit: **1.34 mana per damage absorbed**, down from 2. Absorption amounts, initial costs, duration, physical-only coverage and learning levels stay the same. Removing Arcane Shielding also removes its separate Mage Armor resistance bonus; that bonus is not rolled into baseline Mage Armor.
- **Arcane Meditation:** Keeps its existing 17%/33%/50% mana regeneration while casting and makes your conjured water restore **10%/20%/30% more mana** over the same drinking duration. Applies to every rank of Conjure Water and benefits allies drinking water you create. Its position and prerequisite are unchanged.
- **Ice Walk:** One-point active talent beside Cold Snap (row 5, column 3). Conjures ice under your feet for **5 sec**, with a **30 sec cooldown**, supporting movement across water and through the air, including midair casts. Does not increase movement speed. Landing on the ice preserves accumulated falling damage and can be fatal; you fall if the ice expires over open air. Mana cost, cast time, Cold Snap interaction, platform height and shared use still need design.
- **Frostbite:** Includes a convenience toggle to disable its **5 sec root** when you do not want to freeze targets. This is not an aura or a dispellable buff. Its **5%/10%/15%** trigger chance remains active with the freeze effect off, so procs still grant Fingers of Frost when learned. The root’s dispel rules are unchanged.
- **Fingers of Frost:** One rank in row 3, column 4, connected to and requiring **3/3 Frostbite**. Frostbite procs, including while the freeze effect is toggled off, grant Fingers of Frost, causing your next spell to treat its target as Frozen. The existing 15 sec buff duration is retained. **Improved Blizzard** moves left to row 3, column 3, with its effect unchanged.
- Previous Arcane Drive, Magical Precision, Arcane Reach and Critical Mass changes remain in place.

### Ice Lance source and proposed tuning

The current [Talents Forever export](https://talentsforever.com/data.json), checked October 5, 2026, reports client **1.60.1.70170** and a maximum-rank base damage of **136–160**. This is spell Rank 6, available from source level 56. Other databases can differ by 1 point from level scaling or rounding; this proposal consistently uses the same source as the talent baseline. See `ice-lance-tuning.json` for every source rank, level, cost and calculation.

| Spell rank | Source level | Current base damage | Proposed 0–4 stacks | Proposed 5 stacks |
| --- | --- | --- | --- | --- |
| 1 | 20 | 28–32 | 7–8 | 42–48 |
| 2 | 28 | 34–40 | 9–10 | 51–60 |
| 3 | 34 | 44–52 | 11–13 | 66–78 |
| 4 | 42 | 76–90 | 19–23 | 114–135 |
| 5 | 48 | 95–111 | 24–28 | 143–167 |
| 6 | 56 | 136–160 | 34–40 | 204–240 |

Initial tuning is **25%** of source base damage at 0–4 stacks and **150%** at 5 stacks, rounded to the nearest whole number. The proposal retains **triple damage against Frozen targets**. The source's “300% increased” means four times normal damage, so max-rank full-stack Frozen damage rises from **544–640** to **612–720** (+12.5%). Full-stack non-Frozen damage is +50%. These are base-damage comparisons before spell power and talents; coefficients are not tuned. Earlier ranks are shown for transparency, while the proposed sixth-row talent is first available at level 35. Source mana costs, range and instant cast are retained.

### Spell-change section

Below the trees, three scrollable lists organize changes by **Fire / Arcane / Frost**. Hover or focus an entry for a tooltip; click/tap to expand it. Each entry contains proposed text, beta reference text and design notes.

Frost contains Frost Ward, Ice Block, Ice Lance, the Frostbite freeze-effect toggle and Ice Walk. Fire contains conditional Burn Notice changes to Fireball, Pyroblast, Flamestrike and Ignite. Arcane contains the baseline Mana Shield efficiency change and the Arcane Meditation benefit for Conjure Water. These are proposal descriptions, not effects dynamically simulated when you spend points.

**Add spell change** and **Edit spell change** let you maintain this section. Spell entries are included in JSON backups, share links, Reddit summaries and downloaded HTML. Spell entries and talent descriptions are edited independently, so keep their wording consistent when revising a spell granted by a talent.

**Still open:** Ice Walk cost, cast time and platform interactions; Winter's Chill duration and spell-power scaling; Burn Notice tick/cap/cross-Mage details; Flamestrike stored-damage behavior when targets enter or leave its ground area. These are flagged as unfinished rather than represented as verified game rules.

## Save and share

- **Save draft / Load draft** stores one draft in the current browser, explicitly on request. Reloading shows the published starting state; choose Load draft to restore your saved work. A subsequent Save replaces that draft.
- **Export JSON / Import JSON** moves a draft between browsers and provides a backup. Invalid ranks, overlapping positions, impossible prerequisites, and incompatible baselines are rejected.
- **Copy build link** works from a published HTTP(S) address and includes both builds, the active mode, level, talent edits, title, and notes in the URL fragment. Local-file and localhost previews prompt you to publish first. Large proposals can produce long links; share the exported HTML for those.
- **Download HTML** creates another self-contained `index.html` containing your current build and proposal as its starting state. Upload that file to update your GitHub Pages site. Original beta definitions remain embedded alongside the proposed changes.
- Changes remain local until you explicitly share or publish them. The app has no backend.

## Snapshot and attribution

The baseline is an exact extraction of the `talents.Mage` trees from [Talents Forever's public data export](https://talentsforever.com/data.json), credited to **Chris Baldwin / Talents Forever** under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

- Reference calculator: https://talentsforever.com/mage
- Dataset generated: **2026-10-04**
- Retrieved and visually checked: **2026-10-05**
- Reported beta client: **1.60.1.70170**
- Talent rows/columns, names, every rank description, rank caps, costs, icons and prerequisites are preserved.
- This is a fixed beta snapshot, not an automatically updating feed. It has not been independently verified in the game client. Source tooltip values are displayed as provided, including the source's spell-rank/level conventions.

`mage-baseline.json` is a readable reference copy. Editing that separate file does not modify the page: the calculator's working baseline is in the `baseline-data` JSON script inside `index.html`. The application rules and UI follow it in the `engine-code` and `app-code` scripts. The surrounding interface is an original implementation, not a pixel-for-pixel copy of the source website.

The source's data license does not transfer ownership of Blizzard assets. World of Warcraft, game names, icons, background artwork and tooltip text belong to Blizzard Entertainment. This is an unofficial fan project, not affiliated with Blizzard Entertainment or endorsed by Talents Forever. Keep the source and license attribution when republishing or adapting the dataset; proposals are marked as modifications.

## Verification

The delivered baseline was compared field-for-field with the downloaded source. Automated checks covered tier gates, prerequisite/refund behavior, the 51-point budget, Unicode link round trips, invalid imports, proposal isolation, and 20,000 randomized legal allocation/removal attempts. Browser checks covered spending, blocked refunds, proposal edits, dependent-point refunds, saved draft restoration, responsive layout and embedded-image loading. A real browser-downloaded proposal HTML was reopened successfully and checked to retain both builds, edits, and the original baseline.

SHA-256 of the original full source export: `40b7ea10e82b9b2e8d0112a1bdf35a303b2eb3d3ff26df2736bad51ba0d5d6ea`.

## Proposal icon artwork

Eight custom talents use distinct Blizzard icons from the wider WoW spell catalog, retrieved from Wowhead’s image CDN on October 5, 2026. Conjure Water also uses a water-container icon in the spellbook. Original beta artwork is preserved. All artwork is embedded in the HTML for offline use; no runtime hotlinking is needed. Icons remain Blizzard Entertainment artwork, not part of the talent-data CC BY license. See `icon-sources.json` for exact source URLs and assignments.
