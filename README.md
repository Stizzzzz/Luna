# 🌙 Luna

**Modern username enumeration tool — search for usernames across the web.**

Luna searches 150+ websites and social platforms to find where a username is registered. 

---

## Quick Start
1. Download and unzip the .zip from `Releases` 
2. Run `luna.exe`
3. Type a username and press **Enter** to start searching!

---

## Controls

### Home Screen
| Key | Action |
|-----|--------|
| `Type` | Enter username |
| `Enter` | Start search |
| `Tab` | View/edit site list |
| `F1` | Help |
| `q` | Quit |

### Site List
| Key | Action |
|-----|--------|
| `j/k` or `↑/↓` | Navigate |
| `Space` | Toggle site on/off |
| `a` | Enable all sites |
| `n` | Disable all sites |
| `Tab/Esc` | Back |

### Results
| Key | Action |
|-----|--------|
| `j/k` or `↑/↓` | Navigate |
| `f` | Filter (found only) |
| `e` | Export results |
| `Enter` | Open URL in browser |
| `n` | New search |

---

## Command Line Usage

```bash
# Interactive TUI (default)
luna.exe

# Headless mode
luna.exe --headless <username>

# Export results
luna.exe --headless <username> -o results.json
luna.exe --headless <username> -o results.csv -f csv
luna.exe --headless <username> -o report.html -f html

# Filter by category
luna.exe --headless <username> --categories social,gaming

# Include adult sites (disabled by default)
luna.exe --headless <username> --include-adult

# List all sites
luna.exe --list-sites

# Adjust workers and timeout
luna.exe --headless <username> -w 100 -t 5000
```

---

## Site Categories

| Category | Sites |
|----------|-------|
| Social | Twitter, Instagram, TikTok, Reddit, etc. |
| Developer | GitHub, GitLab, StackOverflow, etc. |
| Gaming | Steam, Discord, Twitch, Xbox, etc. |
| Creative | DeviantArt, ArtStation, Behance, etc. |
| Video | YouTube, Vimeo, TikTok, etc. |
| Music | Spotify, SoundCloud, Bandcamp, etc. |
| Professional | LinkedIn, Glassdoor, etc. |
| + More | Forums, Blogging, Finance, Messaging... |

**151 sites** across **14 categories**

---

## Adding Custom Sites

Create a `.toml` file in `sites/<category>/`:

```toml
[site]
name = "Example"
category = "social"
url_template = "https://example.com/user/{username}"
enabled = true

[detection]
method = "status"
valid_statuses = [200]
invalid_statuses = [404]

[request]
method = "GET"
```

---

## Legal Disclaimer

Luna is intended for **legitimate security research and OSINT purposes only**. Users are responsible for ensuring their use complies with applicable laws and terms of service.

---

## Credits

Built by **Stiz Solutions** 🌙

- Inspired by [Sherlock](https://github.com/sherlock-project/sherlock)

- Site data from [WhatsMyName](https://github.com/WebBreacher/WhatsMyName)
