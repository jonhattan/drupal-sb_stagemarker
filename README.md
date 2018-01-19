# Stage Marker

*This is a left aside module that wants to be released.*

Write marks to watchdog or devel's query log at the beginning and end of each
run stage of page execution.

This is a suite of three modules that compound a instrument to measure Drupal
and help in identifying responsibles of time and memory consumption.

Modules implement hooks that just write marks to devel query log and/or the
watchdog.


## Installation

```
cd sites/all/modules
git clone https://github.com/jonhattan/drupal-sb_stagemarker.git
drush pm-enable sb_stagemarker, sb_stagemarker_before, sb_stagemarker_after
```

## Configuration

Configure devel module to display queries and display time and memory consumption.

Add this to settings.php at your convenience:

```
// Enable devel query log.
$conf['dev_query'] = 1;
$conf['devel_query_display'] = 1;
$conf['devel_query_sort'] = 0;

// Show time and memory consumption.

$conf['dev_mem'] = 1;
$conf['dev_timer'] = 1;

// Hooks to observe. See patches/invoke-hooks.patch
$conf['sb_stagemarker_observed_hooks'] = array(
#  'boot',
#  'init',
#  'page_build',
#  'block_view',
#  'block_view_alter',
#  'page_alter',
#  'exit',
);
```

## Patches

Some stages can't be instrumented without patching core. Some patches are provided in `patches/*` folder.

Apply them at your discretion.

### bootstrap.patch

Writes a mark before each bootstrap phase and after the last phase (`DRUPAL_BOOTSTRAP_FULL`).

### invoke-hooks.patch

Writes a mark before and after invoking hooks. Acts only on observed hooks. See `sb_stagemarker_observed_hooks` variable.


## Viewports

 * Devel queries log.
 * `drush wd-show --tail`


## TODO

 * Find the other versions I have of this module and push updates
 * Find a nice name ('instrument'?)
 * Publish to drupal.org

