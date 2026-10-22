Editor changes by version, newest first. After an update the editor
shows the section of its new version once, in the "What's new" window.

> [!TIP]
> Turn the window off with "Don't show again" or in
> "Settings → General → What's new after updates". The same switch
> turns it back on.

## 1.6.0

- **Descendants are pushed to the A7/19 server.** The A7/19 server does
  not update descendants when their base type changes. Now a push to
  the A7/19 server sends the type together with all its descendants
  from every packet of the configuration, parents first. Pushing a type
  sends the type and its descendants in one request. When a packet is
  pushed, descendants from other packets follow as separate rows in
  the push status window.
- Ancestors are not added. Descendants are not sent to the v26 server:
  it rebuilds them itself.
- The switch is "Settings → General → Push → Push descendants with a
  type". It is on by default.

> [!WARNING]
> Moving a field between a parent and a descendant loses that field's
> values on the A7/19 server. If a descendant has no uid (no `.dbo`),
> the push fails and the message names that type.

- **"What's new" window.** After an update the editor shows once what
  changed in the new version. The text comes from this help article,
  so without a network the window appears on the next start. The full
  change history is under "Help → What's New".
