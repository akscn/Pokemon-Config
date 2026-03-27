# Pokemon Terminal Startup (JaKooLit style)

Pokémon on the left, system info on the right — every new terminal window.

---

## Install required packages

```bash
sudo pacman -S fastfetch
yay -S pokemon-colorscripts-git
```

---

## Step 1 — Copy config-pokemon.jsonc to fastfetch folder

Create the folder if it doesn't exist:
```bash
mkdir -p ~/.config/fastfetch
```

Then copy the file:
```bash
cp config-pokemon.jsonc ~/.config/fastfetch/config-pokemon.jsonc
```

---

## Step 2 — Add the startup line to Fish config

Open your fish config:
```bash
nano ~/.config/fish/config.fish
```

Paste this line **inside** the `if status is-interactive` block:
```fish
pokemon-colorscripts --no-title -s -r | fastfetch -c ~/.config/fastfetch/config-pokemon.jsonc --logo-type file-raw --logo-height 10 --logo-width 5 --logo -
```

It should look like this:
```fish
if status is-interactive
    ...your other stuff...

    # Pokemon-JakooLit
    pokemon-colorscripts --no-title -s -r | fastfetch -c ~/.config/fastfetch/config-pokemon.jsonc --logo-type file-raw --logo-height 10 --logo-width 5 --logo -
end
```

Save with `Ctrl+O` → `Enter` → `Ctrl+X`

---

## Step 3 — Reload Fish

```bash
exec fish
```

---

## File locations summary

| File | Where it goes |
|------|--------------|
| `config-pokemon.jsonc` | `~/.config/fastfetch/config-pokemon.jsonc` |
| pokemon line from `pokemon-startup.fish` | inside `~/.config/fish/config.fish` |
