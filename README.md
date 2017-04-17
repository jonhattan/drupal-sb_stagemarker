# Stage Marker

*This is a left aside module that wants to be released.*

Write marks to watchdog or devel's query log at the beginning and end of each run stage of page execution.

## Usage

```
cd sites/all/modules
git clone https://github.com/jonhattan/drupal-sb_stagemarker.git
drush pm-enable sb_stagemarker, sb_stagemarker_before, sb_stagemarker_after
```

Viewports:

 * Devel queries log.
 * `drush wd-show --tail`


## TODO

 * Branch d6/d7
 * Find the other versions I have of this module and push updates
 * Find a nice name ('instrument'?)
 * Publish to drupal.org

