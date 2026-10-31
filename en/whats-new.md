Editor changes by version, newest first. After an update the editor
shows the section of its new version once, in the "What's new" window.

> [!TIP]
> Turn the window off with "Don't show again" or in
> "Settings → General → What's new after updates". The same switch
> turns it back on.

## 1.7.1

- **A clear message when a token is missing.** If repositories moved to another
  server and you have no access to it, the editor names the server and offers an
  "Open Git settings" button. The message stays until the problem is solved. A
  wrong token gets its own message.
- **Switching right after you enter a token.** Once you save a token in the
  settings, the editor retries moving the repositories to their new address, with
  no restart. Update their contents with "Pull all changes".
- **An honest pull summary.** If some repositories were pulled from their old
  address, the log says how many.

## 1.7.0

- **GitLab alongside GitHub.** The editor works with several git servers at
  once. Set a token per server in "Settings → Git → Server tokens"; it works
  in both SSH and HTTPS modes.
- **Moved repositories.** When the configuration manifest gives a packet an
  address on another server with the same repository name, the editor
  re-points the clone's `origin` when the configuration opens and on bulk
  pull. It switches only if the new address answers; otherwise the clone
  stays on the old server and the log shows a warning. Other projects and
  forks are left alone.
- **WD widget blocks.** `a7dbojs` accepts nested widgets for the v26 server,
  such as `body: Circle { radius: this.size / 2; }`. Packets without blocks
  are unaffected: their `.dbo` does not change.
- **Type review.**
  - Removing a member no longer fails with "member not found".
  - Decisions are applied by uid and as a whole: on an error the files go
    back to their original state.
  - Unanswered members stop the changes from being applied.
  - A field moved to the parent keeps its uid.
  - Changing `extends` also checks descendants, and a descendant's issue is
    shown once, on its own file.
- **Renaming a type.** Every reference in all packets of the configuration
  is updated, along with `.dbo` and `packet.yaml`. Open documents are saved
  first.

- **Clones are safe.** A packet folder with commits but no `packet.yaml` is
  no longer deleted and downloaded again. The editor leaves it as is and
  reports an error.

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
