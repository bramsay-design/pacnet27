[README.md](https://github.com/user-attachments/files/33948368/README.md)
# PACnet '27 "Make the Case" page, v3 (Eloqua)

**Files:** `index.html` is the whole page (fonts, logo, and pixel strip are built in; nothing else needs uploading). `source-assets/` holds the original logo and pixel image for reference only.

## Putting it in Eloqua
1. Landing Pages > create a page with a blank/custom HTML layout, then paste in `index.html`. If the editor wraps your code in its own head/body, paste only the `<style>` block, the `<div id="pc27">…</div>`, and the `<script>`.
2. Publish a draft over HTTPS and check: role buttons switch the email, the email is editable, both Copy buttons work, the price list and the pink deadline tag show, logo and pixel strip load.
3. No form fields or Eloqua tokens are used. Everything is scoped under `#pc27`, so the template's own CSS shouldn't restyle it.

## Dates and prices update on their own
The page reads the visitor's date and switches tier at midnight Pacific:
- Through Nov 6: Early Early Bird, $799
- Nov 7 to Dec 18: Early Bird, $949
- Dec 19 onward: Full registration, $1,099

The price list, deadline tag, and the email text all change with it. No code edits are needed on Nov 7 or Dec 19. Only edit the `tiers` list near the top of the script if a price or date changes.
Preview any date by adding `?asof=2026-11-10` to the page URL (testing only).

## Notes
- An email copied before a cutover keeps the price it had when copied.
- Confirm RegFox flips tiers at midnight Pacific so the page and registration match.
- The Copy button needs HTTPS (Eloqua pages are). If blocked, the email is selected for manual copy.
