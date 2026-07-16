# 1. Clean up any previous broken downloads
rm -f pipx.pyz

# 2. Create a clean, isolated Python environment in your home folder
python3 -m venv ~/.local/share/pipx-venv

# 3. Install pipx cleanly into that environment from the source registry
~/.local/share/pipx-venv/bin/pip install pipx

# 4. Symlink pipx to your local binary folder
mkdir -p ~/.local/bin
ln -sf ~/.local/share/pipx-venv/bin/pipx ~/.local/bin/pipx

# 5. Inject the path into your current ZSH session and verify
export PATH="$HOME/.local/bin:$PATH"
pipx --version
