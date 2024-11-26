# Sonarr with Tailscale Sidecar Configuration

This Docker Compose configuration sets up [Sonarr](https://github.com/Sonarr/Sonarr) with Tailscale as a sidecar container to securely manage and access your media management system over a private Tailscale network. By using Tailscale in a sidecar configuration, you can enhance the security and privacy of your Sonarr instance, ensuring that it is only accessible within your Tailscale network.

## Sonarr

[Sonarr](https://github.com/Sonarr/Sonarr) is an open-source, self-hosted application for managing TV shows in your media collection. It allows you to automatically download TV episodes from Usenet and BitTorrent sources and organize them in your media library. This configuration leverages Tailscale to securely connect to your Sonarr instance, ensuring that your media management interface is protected from unauthorized access and that your instance is accessible only via your private Tailscale network.

## Configuration Overview

In this setup, the tailscale-sonarr service runs Tailscale, which manages secure networking for the Sonarr service. The sonarr service uses the Tailscale network stack via Docker's network_mode: service: configuration. This setup ensures that Sonarr’s web interface and API are only accessible through the Tailscale network (or locally, if preferred), providing an extra layer of security and privacy for your self-hosted media manager.