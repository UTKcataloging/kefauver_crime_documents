# Kefauver Crime Documents OpenRefine Template

This template is based on the [project data dictionary](https://wiki.lib.utk.edu/display/DLP/Kefauver+Crime+Documents+-+Data+Dictionary).

## Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

## Body

```
<mods xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
{{ if(cells['identifier_file'].value != "IGNORE", '<identifier type="local">' + cells['identifier_file'].value +'</identifier>', '')}}
{{ if(cells['PID'].value != "IGNORE", '<identifier type="pid">' + cells['PID'].value +'</identifier>', '')}}
{{ if(cells['title'].value != "IGNORE", '<titleInfo>' + if(cells['title_initial_article'].value != "IGNORE", '<nonSort>' + cells['title_initial_article'].value + '</nonSort>', '') + '<title>' + cells['title'].value + '</title>', '')}}
</mods>
```

## Row Separator

**BLANK**


## Suffix

```
</modsCollection>
```