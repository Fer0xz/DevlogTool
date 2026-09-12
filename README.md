# DevlogTool

A tiny command-line tool for keeping a running developer log (devlog) as a series of numbered Markdown files. Run one script, answer a few prompts, and it drops a new dated log entry into a `logs/` folder using a consistent template.

## Features

- Auto-numbers each entry (`1`, `2`, `3`, ...) based on what's already in `logs/`
- Stamps every entry with the current date and time
- Fills in a consistent Markdown template with sections for lessons learned, what you did, challenges faced, and next steps
- Optional guided prompts to fill in each section right from the terminal (or skip and edit the file by hand later)
- One-click `.bat` launcher for Windows users

## Requirements

- Python 3.7+
- [colorama](https://pypi.org/project/colorama/)

Install the dependency with:

```bash
pip install colorama
```

## Usage

### Windows

Double-click `NewDevlog.bat`. It runs the script and keeps the console window open so you can read the output.

### Any OS

```bash
python MakeNewDevlog.py
```

You'll be prompted for a title, and then asked whether you want to fill in the log's content right away:

```
Current log index: 10 || Date: 12-09-2026 || Time: 21:45

Enter the title of the devlog: Refactored the save system
Do you want to enter the log content manually? (y/n): y
Enter content for 'Lessons learned'. Type 'done' or 'end' to finish:
- Always back up before a big refactor
- done
...
```

Answer `n` to skip manual entry and get a blank template you can fill in yourself later.

A new file is created at `logs/<index>__<DD-MM-YYYY>_<HH-MM>.md`, for example:

```
logs/10__12-09-2026_21-45.md
```

## Template

New entries are generated from `template.md`:

```markdown
# Dev Diary Nr.

## Title

## Date: YYYY-MM-DD | Time: HH:MM

### Lessons learned:
- 

### What I did:
- 

### Challenges faced:
- 

### Next steps:
- 
```

Edit `template.md` to change the sections that get generated for every future entry.

## Roadmap

- [ ] Rework this into a proper UI — something quick and easy to use instead of the current terminal prompts

## Project structure

```
DevlogTool/
├── MakeNewDevlog.py   # Main script: prompts for input and writes a new log
├── NewDevlog.bat       # Windows launcher for the script
├── template.md         # Template used for every new log entry
└── logs/               # Generated devlog entries live here
```
