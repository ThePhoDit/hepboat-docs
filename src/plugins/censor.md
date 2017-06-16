# Censor Plugin

The censor plugin provides administrators and moderators a simple way to filter certain types of malicious and offensive content, such as:

- Invite Links
- URLs
- Inappropriate or Offensive words

This, combined with the Spam plugin can result in a very robust automatic abuse-prevention system.

## Configuration Options

| Option | Description | Type | Default |
|--------|-------------|------|---------|
| levels | A mapping of levels to Censor Configurations. This will match any user with a level that is equal or lower | dict | empty |
| channels | A mapping of channels to Censor Configurations | dict | empty |

### Censor Configuration

| Option | Description | Type | Default |
|--------|-------------|------|---------|
| filter\_zalgo | Whether to filter zalgo text from messages | true |
| filter\_invites | Whether to filter invite links from messages | bool | true |
| invites\_guild\_whitelist | A list of whitelisted guild IDs for invite codes | list | empty |
| invites\_whitelist | A list of whitelisted invite codes or vanities | list | empty |
| invites\_blacklist | A list of blacklisted invite codes or vanities | list | empty |
| filter\_domains | Whether to filter the domains contained within URLs | bool | true |
| domains\_whitelist | A whitelist of domain names | list | empty |
| domains\_blacklist | A blacklist of domain names | list | empty |
| blocked\_tokens | A list of tokens (can appear in the middle of words) that are blacklisted | list | empty |
| blocked\_words | A list of words (must be seperated by a boundary) that are blacklisted | list | empty |

## Configuration Example

```
  censor:
    levels:
      0:
        filter_zalgo: true
        filter_invites: true
        invites_guild_whitelist: [205769246008016897, 272885620769161216]
        invites_whitelist: ['discord-developers', 'discord-testers', 'discord-api', 'events', 'discord-linux', 'gamenight',]
        invites_blacklist: []
        filter_domains: true
        domains_whitelist: []
        domains_blacklist: ['website.net']
        blocked_tokens: ['block']
        blocked_words: ['example' 'of' 'blocked' 'words']
```