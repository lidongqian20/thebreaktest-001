# The Break Test #01 — Can AI reverse-engineer a 19-year-old channel's writing style?

Every week I take one real, messy task and find out exactly where today's best AI
breaks — then I show you the whole test file so you can run it yourself.

**This is test #001.**

---

## The question

Hank Green / `vlogbrothers` has been publishing since 2007. Their writing style is
distinctive and widely admired, and a lot of people want to copy it.

So: **can an AI read a public account's writing and hand back a reusable style
guide that actually reproduces it?**

I set a five-step bar **before** running anything. Then I ran the real test.

---

## The verdict

> # Breaks at Step 3 of 5

| Step | Result |
|---|---|
| 1. Accepts the file at all | ✅ Pass |
| 2. One shot, hands off | 🟡 Partial (1/2 — session contamination, see SCORING.md) |
| **3. Line-by-line fidelity** | ❌ **Fail (4/12)** |
| 4. Holds up on messy input | ✅ Pass |
| 5. Usable as-is | ❌ Fail |

**The one-sentence finding:**

> ChatGPT produced an excellent *analysis* of the vlogbrothers style — ten named
> rhetorical devices, three structural templates, a seven-item lexical fingerprint,
> every claim backed by a quote. Then it wrote a 96-word blurb using **none** of
> those fingerprints.
>
> It can diagnose the style. It cannot reproduce it.

It understands the *category*. It does not possess the *instance*.
`"In which John"` is not a swappable synonym — it is a specific verbal tic, and
the tic **is** the handwriting.

---

## Why this matters (and why it is not "AI is bad")

The blurb it wrote is *good English*. It has a scene, a joke, an argument, and a
callback ending. As a generic video intro, it's publishable.

But it is not vlogbrothers' handwriting. The difference:

- Good writing is an **average of what is good**.
- A real voice is **specifically weird**.

Anything that averages, cannot preserve what makes a voice worth copying.

---

## The files

| Path | What it is |
|---|---|
| `00-samples/` | 8 raw descriptions pulled from vlogbrothers (5 recent + 3 from Jan/Feb 2007), each with source URL, capture date, and stated limitations. `combined-for-gpt.txt` is what was fed to the model. |
| `01-prompt/01-prompt.md` | The exact prompt, verbatim. **Not edited after sending.** |
| `02-versions/02-versions.md` | Model, environment, and reproducibility instructions. |
| `03-raw-output/run-01.txt` | The model's full style analysis (~2,900 words). Verbatim. |
| `03-raw-output/run-02.txt` | The model's 96-word generated blurb. Verbatim. |
| `04-rubric/04-rubric.md` | The five-step pass/fail bar, **fixed before testing**. |
| `04-rubric/SCORING.md` | The score, with a stated reason for every point deducted. |
| `04-rubric/ROUND-2-PROMPT.md` | The exact second-round prompt used for Step 3. |

Evidence rule for this series: **the bar is set before the test runs, and no file
is edited after the fact.** If a threshold turns out to be badly designed, a
`-v2` file is added and the original is kept.

---

## Reproduce it

```powershell
# 1. Pull the samples
yt-dlp --skip-download --write-description --playlist-items 1-5 "https://www.youtube.com/@vlogbrothers/videos"
yt-dlp --skip-download --write-description --playlist-items 1-3 "ytsearch3:vlogbrothers 2007"

# 2. Open ChatGPT on the web. Pick the same model and reasoning setting (see 02-versions).

# 3. NEW session. First message = 01-prompt/01-prompt.md
#    Replace ONLY the last placeholder line with 00-samples/combined-for-gpt.txt

# 4. Second round = 04-rubric/ROUND-2-PROMPT.md
#    Do NOT re-send the samples. That is the entire point of Step 3.
```

> ⚠️ **Known reproducibility gap**: the model was reported to me as `"6sol"`
> (high reasoning). That name does not match OpenAI's published naming, so I have
> recorded it verbatim and flagged it as unverified. See `02-versions/02-versions.md`.
> Until the exact model name is filled in, this test is **not fully reproducible**.
> That limitation is stated rather than papered over.

---

## Honest limitations

1. **Authorship is uncertain.** `vlogbrothers` is a two-person channel
   (John Green + Hank Green). Descriptions do not always state who wrote them.
   The samples are therefore *channel* writing, not cleanly *Hank Green* writing.
   The model independently flagged this too.
2. **Five recent upload dates are unknown.** A rate limit blocked retrieval, so
   they are recorded as `unknown` rather than guessed. See `00-samples/run-notes.txt`.
3. **Descriptions, not spoken word.** This tests *writing* style. Video voiceover,
   timing and editing are not covered.
4. **Step 2 was contaminated.** The user sent the prompt once without replacing
   the placeholder, so samples arrived over two turns. Recorded as 1/2 and flagged
   for retest, because a conclusion built on contaminated data is not a conclusion.
5. **n = 1.** This is one model, one account, one prompt, one day. It is a data
   point, not a law.

---

## The most quotable line

The model's own answer to "what cannot be copied":

> *"An imitator can copy the grammatical intimacy. They cannot manufacture the
> relationships that make the reference meaningful."*

That is a better answer than most humans give.

---

**The Break Test** — one real task, one clear bar, one straight answer.
Full test files published every time. Conclusions you might disagree with included.
