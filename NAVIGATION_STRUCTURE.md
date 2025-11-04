# Article Navigation Structure

This document describes the navigation structure for all articles in the website.

## Navigation Rules

1. **Language Separation**: Articles only navigate within the same language (EN ↔ EN, FR ↔ FR)
2. **Category Separation**: Articles navigate within the same category
3. **Circular Navigation**: Last article links back to first article in category
4. **Single Articles**: Categories with single article have disabled navigation

## English Articles

### Automation & AI (3 articles)
1. `ai-powered-workflow-mcp-docker-n8n.html` ↔ `my-ai-companion-deploying-the-modular-copilot-platform-mcp-server.html` ↔ `the-quest-for-fluid-notes-my-obsidian-livesync-configuration-and-triumphs.html`

### Docker Services (3 articles)
1. `docker-compose-chronicles-overcoming-image-download-challenges.html` ↔ `my-docker-symphony-orchestrating-services-in-my-homelab.html` ↔ `taming-docker-compose-resolving-undefined-volume-errors.html`

### Infrastructure (1 article)
1. `building-homelab-foundation-proxmox.html` (no navigation)

### Network Security (1 article)
1. `the-digital-guardian-of-my-homelab-setting-up-a-secure-reverse-proxy-with-https.html` (no navigation)

### Reference (4 articles)
1. `navigating-my-homelab-essential-urls-and-access-points.html` ↔ `network-architecture-prompt-dns-tls-and-reverse-proxies.html` ↔ `ssl-certificate-configuration-prompt-securing-your-homelab.html` ↔ `tracing-my-homelab-journey-a-roadmap-to-self-hosted-services.html`

### Remote Access (1 article)
1. `the-twingate-connection-mystery-untangling-authentication-failures.html` (no navigation)

## French Articles

### Automation & AI (2 articles)
1. `mcp-configuration-guide-yaml-setup-and-configuration.html` ↔ `my-ai-powered-workflow-integration-of-mcp-docker-and-n8n-for-obsidian.html`

### Infrastructure (5 articles)
1. `building-a-secure-lab-kali-linux-and-pfsense-deployment.html` ↔ `building-the-homelab-foundation-proxmox-ve-installation-and-initial-configuration.html` ↔ `growing-pains-extending-the-disk-of-my-ubuntu-vm-on-proxmox.html` ↔ `my-ai-and-kali-adventures-llm-testing-and-proxmox-debugging.html` ↔ `my-network-rescue-getting-proxmox-and-pfsense-back-online.html`

### Network Security (3 articles)
1. `securing-my-n8n-workflows-a-deep-dive-into-dns-and-tls.html` ↔ `the-ssl-certificate-saga-local-dns-nginx-and-my-homelab.html` ↔ `troubleshooting-pfsense-web-interface-access-a-troubleshooting-story.html`

### Remote Access (1 article)
1. `unlocking-remote-access-my-journey-with-cloudflare-tunnel-and-proxmox.html` (no navigation)

## Implementation Notes

- Navigation links are relative to the current directory
- Disabled navigation uses CSS class `disabled`
- Article titles are extracted from HTML `<title>` tags
- All navigation stays within the same language and category

## Last Updated

Generated on: 2025-11-04 18:44:02.560494