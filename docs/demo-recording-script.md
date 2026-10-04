# Three-minute demo recording script

**For the v1.0.0 terminal release.** Record with the English interface at 85–90
terminal columns. Use the directions and words below; the profile, menu, names and
postcard sentence are synthetic. This walkthrough makes no real meal, health,
price, preference or friend-feedback claim. Target runtime: **2:50**, hard stop 3:00.

## Before recording

1. Unzip the release (or open its checked-out folder) and open Terminal in the
   project directory. Connect the microphone and close unrelated private windows.
2. Set up a fresh disposable directory and launch the explicitly synthetic demo:

   ```sh
   DEMO_DIR="$(mktemp -d /tmp/plate-memory-demo.XXXXXX)"
   python3 plate-memory.py --demo --language en --profile "$DEMO_DIR/friend.json"
   ```

3. Set terminal width to 85–90 columns, hide unrelated panes and notifications,
   leave terminal decoration/color on, and keep the whole menu legible. The temporary
   path is disposable. The menu and profile stay in memory; only the postcard you
   explicitly export will be written there.
4. Rehearse the choices once before recording. Do not prefill, edit or submit any
   real friend's profile. Do not describe the canned guard fixture as live AI.

## Timed run

| Time | Terminal actions | Spoken line / camera cue |
|---|---|---|
| 0:00–0:17 | Show the welcome and four main destinations. Pause on the bowls and the empty chair theme. | “We ate together every day in high school. Now we’re at different universities. Plate Memory is a small way to save each other a seat.” |
| 0:17–0:55 | Press `6` for More, type `demo`, then type `weekend`. Let the report appear. Slowly scroll over the Saturday date, `WEEKDAY_OUT_OF_SCOPE`, and `HIGH_RISK_HUMAN_REVIEW_REQUIRED`. | “Same memory, new context. The weekday note doesn’t carry into Saturday. The allergy note still asks a person to check with the preparer. The Python guard makes that call. This screen uses the clearly labeled canned weekend fixture; it does not call the model.” |
| 0:55–1:25 | At the table, press `1` Find something to eat, `2` cafeteria, type `something warm`, then press `1` for an idea. Pause on **Food family**, **On the menu**, and the nearby-match label. | “When all you know is that you want something warm, offline food references offer a few directions. They don’t claim a shop has it, or guess ingredients, price or nutrition.” |
| 1:25–1:48 | Press `4` Similar ideas, pick `1`, then `1` Pick. Pause on “Nothing has been ordered or recorded as eaten” and the cafeteria next step. | “The related choices help you keep browsing. Choosing one is just a plan: check the cafeteria board before you walk over.” |
| 1:48–2:34 | At the table press `4` Until our next meal. Type `Synthetic Jesse`, `Synthetic Bro`, and `Different campuses. Still my lunch buddy. See you at the table soon. 🥣`. Answer `yes` to include the food, `1` Export, `1` share folder, `yes` to include the project link. Press Return at the save path to use the temporary folder's default. Hold on the preview and the **Saved locally. Nothing was sent.** confirmation and paths. | “The card is a little note from one friend to another. The meal is identified as an idea for next time. The export makes a real HTML card, text copy and importable lunchbox file, with a checksum manifest. I choose whether to include the public quick-start link; nothing sends automatically.” |
| 2:34–2:50 | Press `0` to close. At the shell prompt, open the exported card: `open "$DEMO_DIR"/postcards/postcard-*.html`. Let the standalone card fill the screen. | “The drawing is fictional; the words are mine. The HTML carries its artwork with it and opens offline. That’s Plate Memory: practical food ideas, careful memory decisions, and a place for your friend at the table.” |

## Exact interactive input order

This is a cue sheet, not a paste-all-at-once macro; wait for each prompt so keystrokes
land in the intended field:

```text
6
demo
weekend
1
2
something warm
1
4
1
1
yes
4
Synthetic Jesse
Synthetic Bro
Different campuses. Still my lunch buddy. See you at the table soon. 🥣
yes
1
1
yes
[press Return at save path]
0
```

Enter `demo` exactly as shown. The output order is: More → canned guard scenario → table → food search →
similar ideas → pick → postcard → export bundle → table → close. If a page takes
longer than expected, trim pauses and narration; don’t rush through the allergy
review distinction.

## Accuracy and edit notes

- The guard screen says `canned-demo`. Call it a deterministic replay from the
  checked-in synthetic fixture. The app's optional menu review uses a local open
  model to extract candidate food phrases; the model never decides memory permission,
  scope, risk or the final guard verdict. Do not imply this canned scene just ran AI.
- Food ideas come from the attributed offline name catalog and bounded browsing
  directions. Exact price, stock, portions, ingredients and nutrition are unknown.
- The postcard and local share folder are genuinely exported. The fictional
  illustration depicts generic friends, not Jesse or Harold. Keep the invented demo
  line labeled synthetic whenever it is shown outside the UI.
- This demonstrates a usable local v1.0.0, not a real user trial. Leave all factual
  Harold reaction and preference claims out until he has actually tried it.
- Release package: [v1.0.0](https://github.com/Jesse-Zeng423/that-bro-who-ate-with-you-everyday-back-in-highschool/releases/tag/v1.0.0).
