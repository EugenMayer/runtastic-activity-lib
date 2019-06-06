# Runtastic-Activity-Parser

A simple parser to convert activities from runtastic to a basic GPX format.
This can be used to export rRuntastic activities and import them into Strava or other services.

Hint: as for now, you can only import date and GPS data, e.g. you heartrate can not be imported

## Usage

### 1. Export your data
To export your activities out of Runtastic, you need to login into their Web-App

1. Login to [runtastic.com](https://www.runtastic.com)
2. Navigate to your profile > Settings. In the settings menu you can 
find a point called "Export". There you can request all your personal data
stored by runtastic. After few minutes you will get a mail with a download link.
3. Downloading the package of your whole personal data. The package contains 
a folder 'Sport-sessions'. This folder includes all your activities in seperated JSON files. 

We only need the sub-folder Sport-sessions/GPS-data - not the whole folder. This export does include all your other data too.

### 2. Convert your data

[Download the runtastic-activitiy-parser.jar](https://github.com/EugenMayer/runtastic-activity-parser/releases/download/0.0.1/runtastic-activity-parser.jar) release from the Github page and the run

```bash
java -jar runtastic-activity-parser.jar ~/Downloads/runtastic_export/Sport-sessions/GPS-data ~/Downloads/converted-data
```

Now you have all your data in `~/Downloads/converted-data`

Hint: Of course, source folder and destination folder are just examples and can be anything.

### 3. Import your data

This would be fro Strava, other can work too

1. Go to https://www.strava.com/upload/select
2. Now upload all your converted data ( `.gpx files` ) from `~Downloads/converted-data` (you can select up to 25 files at once)

## Building

This is a Java Project build with maven.
Build the project with \
```bash
mvn package 
```

## Credits

All of those to the initial authori [mato1092](https://github.com/mato1092/runtastic-activity-lib) - he did the entire work.
