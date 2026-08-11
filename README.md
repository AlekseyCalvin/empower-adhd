# __ _____ ____ __ EMPOWER-ADHD __ _____ ____ __ 
<p align="center">
  <strong align="center">ADHD-empowering outputs. To make ADHD diagnoses more wanted!</strong>
</p>
<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/github/license/ayghri/i-have-adhd?style=flat" alt="License"></a>
</p>

<p align="center">
  <strong title="English" aria-label="English">🇬🇧</strong> ·
  <a href=".github/readme/README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳</a> ·
  <a href=".github/readme/README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷</a> ·
  <a href=".github/readme/README.ja.md" title="日本語" aria-label="日本語">🇯🇵</a> ·
  <a href=".github/readme/README.vi.md" title="Tiếng Việt" aria-label="Tiếng Việt">🇻🇳</a> ·
  <a href=".github/readme/README.ko.md" title="한국어" aria-label="한국어">🇰🇷</a>
</p>

## Install
🔗 [Installation Instructions](INSTALL.md)

## What it does
Shape output to genuinely aid and support a user with ADHD. <br>
Revision of the popular [`i-have-adhd` skill/plugin](https://github.com/ayghri/i-have-adhd) adding a (*very ADHDuman-styled*) preamble on the traits of some ADHD personalities. This also reworks the source skill's rules to encourage agents to serve project aims & support ADHD-folks... <br>
How?
By doing what agents already do, but **better**! <br>
You know: by actually taking over tedious tasks, researching to solve problems you actually care about, & communicating pertinently to the same. <br>
Invoke via `/empower-adhd`; stays on until the agent hears `"stop adhd powers"`. <br>
And in a flash, all magick's gone...

## Tune it
Fork, edit `skills/empower-adhd/SKILL.md`, then swap your copy in:

```bash
claude plugin uninstall empower-adhd            # drop the upstream copy first:
claude plugin marketplace remove empower-adhd   # fork and upstream share both names
claude plugin marketplace add <your-username>/empower-adhd
claude plugin install empower-adhd@empower-adhd
```

Restart Claude Code, then re-invoke `/empower-adhd`.

## Credits

The [original skill/plugin](https://github.com/ayghri/i-have-adhd) by [Ayoub Ghriss](https://github.com/ayghri) is based on *The Adult ADHD Tool Kit* by J. Russell Ramsay and Anthony L. Rostain. Adapted for how an LLM should respond, not how a human should organize their day.

## License

MIT.

Star ⭐ if it saved you one scroll past one "Great question!"
