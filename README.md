# patent skill installation

This package contains a Codex skill named `patent`.

## Files

```text
patent/
  SKILL.md
  references/
    disclosure_style_guide.md
  assets/
    technical_disclosure_template.md
    input_brief_template.md
  examples/
    example_prompt.md
```

## Recommended installation paths

Use the location that matches where Codex actually runs.

### WSL/Linux

```bash
mkdir -p ~/.agents/skills
cp -r patent ~/.agents/skills/
```

### Windows PowerShell

```powershell
New-Item -ItemType Directory -Force "$HOME\.agents\skills" | Out-Null
Copy-Item -Recurse -Force ".\patent" "$HOME\.agents\skills\"
```

### Repo-specific installation

Put the folder here:

```text
your-repo/
  .agents/
    skills/
      patent/
        SKILL.md
```

## Use in Codex

Restart Codex after installing. Then use one of:

```text
/skills
```

Select `patent`.

Or explicitly invoke it:

```text
$patent 请根据以下技术要点撰写技术交底书……
```

Or rely on implicit triggering by saying:

```text
请帮我写一份专利技术交底书……
```

## If Codex cannot find the skill

1. Confirm the directory contains `SKILL.md` directly:
   ```text
   ~/.agents/skills/patent/SKILL.md
   ```
2. Confirm Codex is running in the same environment where you installed the skill.
   - If Codex runs in WSL, install under WSL home, such as `/home/syj/.agents/skills/patent`.
   - If Codex runs in Windows, install under Windows home, such as `C:\Users\<YourName>\.agents\skills\patent`.
3. Restart Codex and run `/skills`.
4. If still unavailable, add the skill path explicitly in `~/.codex/config.toml`:
   ```toml
   [[skills.config]]
   path = "/home/syj/.agents/skills/patent"
   enabled = true
   ```
   On Windows, use a Windows path such as:
   ```toml
   [[skills.config]]
   path = "C:\\Users\\<YourName>\\.agents\\skills\\patent"
   enabled = true
   ```
