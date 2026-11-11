FROM mcr.microsoft.com/devcontainers/base:bookworm

# Bun (pin matches packageManager in imp-ts).
# Symlink into /usr/local/bin so login shells (which reset PATH) still find it.
ENV BUN_INSTALL=/usr/local/bun
ENV PATH="${BUN_INSTALL}/bin:${PATH}"
RUN curl -fsSL https://bun.sh/install | bash -s "bun-v1.3.13" \
 && ln -sf /usr/local/bun/bin/bun /usr/local/bin/bun \
 && ln -sf /usr/local/bun/bin/bunx /usr/local/bin/bunx
