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
{{ if(cells['rights'].value != "IGNORE", '<accessCondition type="use and reproduction"' + if(cells['rights_URI'] != "IGNORE", ' xlink:href="' + cells['rights_URI'].value + '"', '') + '>' + cells['rights'].value + '</accessCondition>', '')}}
{{ if(cells['rights_holder_name'].value != "IGNORE", '<name' + if(cells['rights_holder_name_authority'].value != "IGNORE", ' authority="' + cells['rights_holder_name_authority'].value + '"', '') +
if(cells['rights_holder_name_type'].value != "IGNORE", ' type="' + cells["rights_holder_name_type"].value + '"', '') + if(cells['rights_holder_name_URI'].value != "IGNORE", 'valueURI="' + cells['rights_holder_name_URI'].value + '"', '') + '><namePart>' + cells['rights_holder_name'].value + '</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cph" type="text">Copyright holder</roleTerm></role></name>', '')}}
{{if(cells['item_type'].value != "IGNORE", '<typeOfResource>' + cells['item_type'].value + '</typeOfResource>', '')}}
{{if(cells['date_text'].value != "IGNORE", '<originInfo><dateCreated' + if(cells['date_qualifier'].value != "IGNORE", ' qualifier="' + cells['date_qualifier'].value + '"', '') + '>' + cells['date_text'].value + '</dateCreated>' + if(cells['date_key'].value != "IGNORE", '<dateCreated encoding="edtf" keyDate="yes">' + cells['date_key'].value + '</dateCreated>', '') + '</originInfo>', '')}}
{{if(cells['form'].value != "IGNORE", '<physicalDescription><form' + if(cells['form_URI'].value != "IGNORE", ' authority="aat" valueURI="' + cells['form_URI'].value + '"', '') + '>' + cells['form'].value + '</form>' + if(cells['extent'].value != "IGNORE", '<extent>' + cells['extent'].value + '</extent>', '') + '</physicalDescription>', '')}}
</mods>
```

## Row Separator

**BLANK**


## Suffix

```
</modsCollection>
```