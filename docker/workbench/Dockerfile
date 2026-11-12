FROM mcr.microsoft.com/devcontainers/base:bookworm

COPY --from=ghcr.io/oras-project/oras:v1.2.2 /bin/oras /usr/local/bin/oras

ARG SILENTORB_AGENTS_PUBLISHING_VERSION=0.1.0
ARG SILENTORB_AGENTS_PLANNING_VERSION=0.1.0

RUN mkdir -p /opt/silentorb-agents/silentorb-agents-publishing \
             /opt/silentorb-agents/silentorb-agents-planning \
 && cd /opt/silentorb-agents/silentorb-agents-publishing \
 && oras pull "ghcr.io/silentorb/silentorb-agents-publishing:${SILENTORB_AGENTS_PUBLISHING_VERSION}" \
 && cd /opt/silentorb-agents/silentorb-agents-planning \
 && oras pull "ghcr.io/silentorb/silentorb-agents-planning:${SILENTORB_AGENTS_PLANNING_VERSION}" \
 && chown -R vscode:vscode /opt/silentorb-agents
