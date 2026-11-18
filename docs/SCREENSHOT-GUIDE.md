# Capturing `screenshot.png` (do this only after the repo is published)

The bounty requires a screenshot of **this repository's own page on GitHub**, with the README rendered
on it, committed as **`screenshot.png` at the repository root**. It cannot be taken before the
repository exists on GitHub, and it must not be faked, rendered locally, or borrowed from the kit's
starter (the starter's sample capture shows a sample repository that is not ours — submitting it would
fail the checks and misrepresent the entry).

## Constraints from the rules (check: `guide_page`)

- File name and place: `screenshot.png`, repository **root** (not in `docs/`).
- Format: a real PNG, JPEG or WebP image (the file keeps the name `screenshot.png`).
- Size: at most **8 MB** and at most **16,000,000 pixels** in total.
- Content: the repository page on GitHub with the README showing. The board, the Feed and the entry
  cards display a **square crop from the top** of the image, so the top of the capture must show the
  repository name and the first lines of the README. A full-page capture at 1x (normal) scale fits the
  pixel cap; a 2x/retina full-page capture of a long page may exceed it.

## Steps

1. Push the repository to GitHub (public) and confirm the README renders on the repo home page.
2. Open `https://github.com/<owner>/<repo>` in a desktop browser at a window width of about 1280 px,
   light theme, zoom 100%. Scroll to the very top.
3. Take a full-page screenshot:
   - Firefox: right-click → "Take Screenshot" → "Save full page".
   - Chrome/Edge: DevTools (F12) → Ctrl/Cmd+Shift+P → "Capture full size screenshot".
   - Or any full-page capture extension that saves at 1x scale.
4. Verify the file before committing (either command set works):

   ```sh
   ls -l screenshot.png                      # must be ≤ 8,388,608 bytes
   python3 -c "from PIL import Image; im=Image.open('screenshot.png'); print(im.size, im.size[0]*im.size[1])"
   # width*height must be ≤ 16,000,000; if it is over, re-capture at 1x or trim the page length
   ```

5. Eyeball the top of the image: repository name visible, badge lines and the guide's title visible.
6. Save it as `screenshot.png` in the repository root, commit, and push. The submission commit must
   include it — the entry is refused without it.
7. Do not create a `.github/README.md` at any point; GitHub would render that instead of the guide and
   the entry is refused.
