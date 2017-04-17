# Stage Marker

*This is a left aside module that wants to be released.*

Write marks to watchdog or devel's query log at the beginning and end of each
run stage of page execution.

This is a suite of three modules that compound a instrument to measure Drupal
and help in identifying responsibles of time and memory consumption.

Modules implement hooks that just write marks to devel query log and/or the
watchdog.

Additionally a set of patches are provided (see `patches/*`)) to enable
measuring at some internal points where we can't hook and patching is the only
option.


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
```

Additionally, if you plan to apply any of the available patches, add this to settings.php:

```
require_once 'sites/all/modules/sb_stagemarker/sb_stagemarker.module';
```


## Viewports

 * Devel queries log.
 * `drush wd-show --tail`


## TODO

 * Find the other versions I have of this module and push updates
 * Find a nice name ('instrument'?)
 * Publish to drupal.org

