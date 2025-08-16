# ZenPack
Automated sound pack manager. Unpack, clean, sort, and organize massive sample libraries into a consistent structure with one command.

# 🎵 ZenPack

**ZenPack** is an automated sound pack manager designed for producers who want order instead of chaos.  
It unpacks, cleans, sorts, and organizes massive sample libraries (like Cymatics, Remnant, YouTuber packs, etc.) into a **consistent, professional structure**.

---

## ✨ Features

- **Recursive Unpack**  
  Extract `.zip` and `.rar` archives (with 7-Zip support) — handles nested archives automatically.

- **Smart Cleanup**  
  Remove junk files (`.DS_Store`, thumbnails, metadata) and irrelevant leftovers.

- **Structure Sort**  
  Copy or move your raw packs into a locked, canonical folder tree:  
01 - DRUMS
├── Kicks
├── 808s
├── Snares
├── Cymbals
└── Percussion
02 - LOOPS
├── Drum Loops
└── Melodic Loops
03 - ONE SHOTS
04 - MIDI
└── Melodic MIDI
05 - FX
├── Risers
├── Impacts
├── Atmospheres
└── Unknown (edge cases)
09 - REFERENCE
├── Documentation
├── Scripts
└── Ableton Analysis

markdown
Copy
Edit

- **Post-Tidy**  
Auto-classify ambiguous files in *Unknown* (e.g., field recordings → Atmospheres, melodic stems → Melodic Loops, `.mid` → Melodic MIDI).

- **Tree Scan**  
Generate a `tree_log.txt` snapshot of your library for sanity checks and audits.

- **Duplicate Handling**  
Choose `skip`, `rename`, or `overwrite` when conflicts occur.

---

## 🚀 Usage

### 1. Clone Repo
```bash
git clone https://github.com/yourusername/zenpack.git
cd zenpack
2. Basic Workflow
powershell
Copy
Edit
# Recursive unpack
python unzip_unpack_recursive.py --source "PATH\TO\LIBRARY" --dest "PATH\TO\LIBRARY"

# Cleanup
python cleanup_irrelevant.py --root "PATH\TO\LIBRARY" --commit

# Structure sort (copy mode)
python structure_sort.py --root "PATH\TO\LIBRARY" --out "PATH\TO\LIBRARY\LIBRARY_SORTED"

# Move mode with rename duplicates
python structure_sort_move.py --root "PATH\TO\LIBRARY" --out "PATH\TO\LIBRARY\LIBRARY_SORTED" --on-duplicate rename

# Post-tidy
python post_sort_tidy_v3.py --root "PATH\TO\LIBRARY\LIBRARY_SORTED" --commit

# Tree scan
python tree_scan.py --root "PATH\TO\LIBRARY\LIBRARY_SORTED" --max-depth -1
