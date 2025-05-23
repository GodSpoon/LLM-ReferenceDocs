-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
---
title: Use proxy url
sidebar_position: 17
---

# Configure CLI for Microsoft 365 to use a proxy

If you are behind a corporate proxy, you'll be able to use the CLI for Microsoft 365 when the environment variable `HTTP_PROXY` or `HTTPS_PROXY` is set.

## Understanding Proxy URL

When using a proxy, it's important to understand the different parts of a proxy URL. A proxy URL typically consists of the following elements:

- **protocol**: The protocol used by the proxy server, such as `HTTP`, `HTTPS`, or `SOCKS`
- **username and password**: if the proxy server requires authentication, you will need to provide a username and password
- **host**: the hostname or IP address of the proxy server
- **port number**: the port number on which the proxy server is listening. Defaults to 443 for the `HTTPS` protocol, otherwise it defaults to 80 when not provided
