# tmux

Конфиг tmux: тема gruvbox dark, truecolor, копирование в системный буфер. Работает на macOS и Linux, нужен tmux 3.2+ (Debian 12, Ubuntu 22.04 и новее).

## Установка

```sh
git clone git@github.com:lawrence-naumov/tmux.git ~/.tmux-config
ln -sf ~/.tmux-config/tmux.conf ~/.tmux.conf
tmux source-file ~/.tmux.conf   # если tmux уже запущен
```

## Копирование

- Выделение мышью копирует при отпускании кнопки. Двойной клик — слово, тройной — строка.
- `prefix` `[` — режим копирования (клавиши vi): `v` — выделение, `Ctrl-v` — прямоугольник, `y` или `Enter` — скопировать.

Куда попадает текст:

| Система | Утилита |
|---|---|
| macOS | `pbcopy` |
| Linux, Wayland | `wl-copy` (пакет `wl-clipboard`) |
| Linux, X11 | `xclip` или `xsel` |
| По SSH, сервер без графики | OSC 52: буфер локального терминала, если он это поддерживает (iTerm2, Ghostty, kitty, Alacritty, WezTerm) |

Утилита выбирается при загрузке конфига. Если поставил её позже — `tmux source-file ~/.tmux.conf`.
