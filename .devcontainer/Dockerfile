# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.209.6/containers/rust/.devcontainer/base.Dockerfile

# [Choice] Debian OS version (use bullseye on local arm64/Apple Silicon): buster, bullseye
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/rust:0-${VARIANT}

# [Optional] Uncomment this section to install additional packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# Utility for Cargo.toml
RUN su vscode -c "cargo install cargo-edit cargo-watch cargo-make cargo-generate wasm-pack"

# npm
RUN su vscode -c "npm install -g npm npm-check-updates"

# Starship
RUN sh -c "$(curl -fsSL https://starship.rs/install.sh)" -- --yes \
    && rm -rf /home/"${USERNAME}"/.zshrc \
    && echo 'eval "$(starship init zsh)"' >> /home/"${USERNAME}"/.zshrc
