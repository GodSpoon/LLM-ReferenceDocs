<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - ADAPTIVECARD Commands Reference

*This is an automatically generated condensed reference of all ADAPTIVECARD commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-07-01*

---

## Table of Contents

- [adaptivecard-send](#adaptivecard-send)

---

## adaptivecard-send

### Syntax
```
m365 adaptivecard send [options]
```

### Example
```
m365 adaptivecard send --url https://contoso.webhook.office.com/webhookb2/EXAMPLE-GUID-PLACEHOLDER@EXAMPLE-GUID-PLACEHOLDER/IncomingWebhook/fcc6565ec7a944928bd43d6fc193b258/EXAMPLE-GUID-PLACEHOLDER --title "CLI for Microsoft 365 v3.4"```

### Remarks
Using this command you can send either a predefined or a custom adaptive card to the specified URL. To send a predefined adaptive card, specify one or more options: `title`, `description`, `imageUrl`, `actionUrl`. To specify a custom card, specify the card's JSON contents using the `card` option.

When sending both predefined and custom cards, you can specify arbitrary options. With predefined cards, these options will be listed in a FactSet. With custom card, you control how the data will be presented on the card.

The predefined card is automatically adjusted based on which options have been specified (`title`, `description`, `imageUrl`, `actionUrl`). If you don't specify a particular option, that portion of the card will not be included in the sent card.

If your custom card is a card template (card with placeholders like `${title}`), you can fill it with data either by specifying the complete data object using the `cardData` option, or by passing any number of arbitrary options that will be mapped onto the card. The arbitrary properties should not match any of the global options like `output`, `query`, `debug`, etc. Data options like `title`, `description`, `imageUrl` and `actionUrl` will be mapped onto the card as well.

:::warning[Escaping JSON in PowerShell]

When using the `--card` and `--cardData` options it's possible to enter a JSON string. In PowerShell 5 to 7.2 [specific escaping rules](./../../user-guide/using-cli.mdx#escaping-double-quotes-in-powershell) apply due to an issue. Remember that you can also use [file tokens](./../../user-guide/using-cli.mdx#EXAMPLE_SECRET_VALUE_PLACEHOLDER) instead.

:::



---
