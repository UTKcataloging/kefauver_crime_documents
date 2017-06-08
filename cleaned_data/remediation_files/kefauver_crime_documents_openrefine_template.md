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
{{if(cells['date_text'].value != "IGNORE", '<originInfo><dateCreated' + if(cells['date_qualifier'].value != "IGNORE", ' qualifier="' + cells['date_qualifier'].value + '"', '') + '>' + cells['date_text'].value + '</dateCreated>' + if(cells['date_key'].value != "IGNORE", '<dateCreated encoding="edtf" keyDate="yes">' + cells['date_key'].value + '</dateCreated>', '') + if(cells['date_publication'].value != "IGNORE", '<dateIssued>' + cells['date_publication'].value + '</dateIssued>', '')+'</originInfo>', '')}}
{{if(cells['form'].value != "IGNORE", '<physicalDescription><form' + if(cells['form_URI'].value != "IGNORE", ' authority="aat" valueURI="' + cells['form_URI'].value + '"', '') + '>' + cells['form'].value + '</form>' + if(cells['extent'].value != "IGNORE", '<extent>' + cells['extent'].value + '</extent>', '') + '</physicalDescription>', '')}}
<relatedItem displayLabel="Collection" type="host"'><titleInfo><title>Estes Kefauver Papers</title></titleInfo><identifier>MPA.0144</identifier></relatedItem>
{{if(cells['name'].value != "IGNORE", '<name' + if(cells['name_authority'].value != "IGNORE", ' authority="' + cells['name_authority'].value +'"', '') +  if(cells['name_type'].value != "IGNORE", ' type="' + cells['name_type'].value +'"', '') + "><namePart>" + if(cells['name'].value != "IGNORE", cells['name'].value, '') + "</namePart><role><roleTerm" + ">" + if(cells['name_role'].value != "IGNORE", cells['name_role'].value, '') + "</roleTerm></role></name>", '')}}
{{if(cells['name1'].value != "IGNORE", '<name' + if(cells['name_authority1'].value != "IGNORE", ' authority="' + cells['name_authority1'].value +'"', '') +  if(cells['name_type1'].value != "IGNORE", ' type="' + cells['name_type1'].value +'"', '') + "><namePart>" + if(cells['name1'].value != "IGNORE", cells['name1'].value, '') + "</namePart><role><roleTerm" + ">" + if(cells['name_role1'].value != "IGNORE", cells['name_role1'].value, '') + "</roleTerm></role></name>", '')}}
<location><physicalLocation>University of Tennessee, Knoxville. Special Collections</physicalLocation></location>
{{if(cells['abstract'].value != "IGNORE", '<abstract>' + cells['abstract'].value + '</abstract>', '')}}
{{if(cells['genre_URI'].value != "IGNORE", '<genre authority="lcgft" authorityURI="http://id.loc.gov/authorities/genreForms" valueURI="' + cells['genre_URI'].value + '">' + cells['genre'].value + '</genre>', '')}}
<language><languageTerm type="code" authority="iso639-2b">eng</languageTerm></language>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>Kefauver Crime Documents</title></titleInfo></relatedItem>
{{if(cells['public_note'].value != "IGNORE", '<note>' + cells['public_note'].value + '</note>', '')}}
<recordInfo><recordContentSource>University of Tennessee, Knoxville. Libraries</recordContentSourc>
<languageOfCataloging>
         <languageTerm type="code" authority="iso639-2b">eng</languageTerm>
      </languageOfCataloging>
      <recordOrigin>Created and edited in general conformance to MODS Guidelines (Version 3.5).</recordOrigin></recordInfo>
{{if(cells['subject_geographic'].value != "IGNORE", '<subject><geographic' + if(cells['subject_geographic_authority'].value != "IGNORE", ' authority="' + cells['subject_geographic_authority'].value + '"', '') + '>' + cells['subject_geographic'].value + '</geographic></subject>' , '')}}
{{if(cells['subject_geographic1'].value != "IGNORE", '<subject><geographic' + if(cells['subject_geographic_authority1'].value != "IGNORE", ' authority="' + cells['subject_geographic_authority1'].value + '"', '') + '>' + cells['subject_geographic1'].value + '</geographic></subject>' , '')}}
{{if(cells['subject_name'].value != "IGNORE", '<subject><name' + if(cells['subject_name_authority'].value != "IGNORE", ' authority="' + cells['subject_name_authority'].value + '"', '') + if(cells['subject_name_type'].value != 'IGNORE', ' type="' + cells['subject_name_type'].value + '"', '') + '><namePart>' + cells['subject_name'].value + '</namePart></name></subject>', '')}}
</mods>
{{if(cells['subject_name1'].value != "IGNORE", '<subject><name' + if(cells['subject_name_authority1'].value != "IGNORE", ' authority="' + cells['subject_name_authority1'].value + '"', '') + if(cells['subject_name_type1'].value != 'IGNORE', ' type="' + cells['subject_name_type1'].value + '"', '') + '><namePart>' + cells['subject_name1'].value + '</namePart></name></subject>', '')}}
{{if(cells['subject_topic'].value != "IGNORE", '<subject><topic' + if(cells['subject_topic_authority'].value != "IGNORE", ' authority="' + cells['subject_topic_authority'].value + '"', '') + '>' + cells['subject_topic'].value + '</topic></subject>', '')}}
{{if(cells['subject_topic1'].value != "IGNORE", '<subject><topic' + if(cells['subject_topic_authority1'].value != "IGNORE", ' authority="' + cells['subject_topic_authority1'].value + '"', '') + '>' + cells['subject_topic1'].value + '</topic></subject>', '')}}
{{if(cells['subject_topic2'].value != "IGNORE", '<subject><topic' + if(cells['subject_topic_authority2'].value != "IGNORE", ' authority="' + cells['subject_topic_authority2'].value + '"', '') + '>' + cells['subject_topic2'].value + '</topic></subject>', '')}}
{{if(cells['subject_topic3'].value != "IGNORE", '<subject><topic' + if(cells['subject_topic_authority3'].value != "IGNORE", ' authority="' + cells['subject_topic_authority3'].value + '"', '') + '>' + cells['subject_topic3'].value + '</topic></subject>', '')}}
```

## Row Separator

**BLANK**


## Suffix

```
</modsCollection>
```