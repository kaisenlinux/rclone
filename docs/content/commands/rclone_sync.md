---
title: "rclone sync"
description: "Make source and dest identical, modifying destination only."
slug: rclone_sync
url: /commands/rclone_sync/
# autogenerated - DO NOT EDIT, instead edit the source code in cmd/sync/ and as part of making a release run "make commanddocs"
---
# rclone sync

Make source and dest identical, modifying destination only.

## Synopsis


Sync the source to the destination, changing the destination
only.  Doesn't transfer files that are identical on source and
destination, testing by size and modification time or MD5SUM.
Destination is updated to match source, including deleting files
if necessary (except duplicate objects, see below).

**Important**: Since this can cause data loss, test first with the
`--dry-run` or the `--interactive`/`-i` flag.

    rclone sync -i SOURCE remote:DESTINATION

Note that files in the destination won't be deleted if there were any
errors at any point.  Duplicate objects (files with the same name, on
those providers that support it) are also not yet handled.

It is always the contents of the directory that is synced, not the
directory so when source:path is a directory, it's the contents of
source:path that are copied, not the directory name and contents.  See
extended explanation in the `copy` command above if unsure.

If dest:path doesn't exist, it is created and the source:path contents
go there.

**Note**: Use the `-P`/`--progress` flag to view real-time transfer statistics

**Note**: Use the `rclone dedupe` command to deal with "Duplicate object/directory found in source/destination - ignoring" errors.
See [this forum post](https://forum.rclone.org/t/sync-not-clearing-duplicates/14372) for more info.


```
rclone sync source:path dest:path [flags]
```

## Options

```
      --create-empty-src-dirs   Create empty source dirs on destination after sync
  -h, --help                    help for sync
```

See the [global flags page](/flags/) for global options not listed here.

## SEE ALSO

* [rclone](/commands/rclone/)	 - Show help for rclone commands, flags and backends.

