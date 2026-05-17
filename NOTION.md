## Notion Conversion

### Overview
KIM can now export markdown files in a compatible format for Notion import. Notion has issues importing markdown files with media links unless the markdown and media are wrapped into a zip file. A new switch has been added (`-no`) to export in this special format. Once exported from Keep using the `-no` option you must then use the "Settings / Import" menu option in the Notion UI to import the ZIP file successfully. 

### Steps for Migrating to Notion
  (be sure to run a test on a small set of notes first!)
- Run KIM (example `python kim.py -no -b #arthistory` or `python kim.py -no -cd "> 2026-01-01"`). Just be sure to use the `-no` option - see EXAMPLES.md
- Open the Notion app and select "Settings" and the "Import" menu - then choose the main "Import your content to Notion" option
- Find the folder where KIM exported the zipped markdown files called `notion/keepexport.zip` in your export folder
- Select the single zip file in Notion using "choose a file" (you can ignore "Text & Markdown")
- Run the import in Notion
- All markdown files will end up in the Notion sidebar menu under the `keepexport` folder


If you want to export all your Keep notes (run both `python kim.py -no -d -b --all` and `python kim.py -no -d -a -b --all` to export both active and archive (`-a`) notes). The `-d` option removes duplicate labels in notes - e.g., if you have both #mytag in the note and the label 'mytag' as well. **WARNING! The zip file will be overwritten if you export archive notes right after the main notes. Be sure to move or copy the zip file first after exporting the main notes.**

All image media types should transfer (images and drawings). Audio files will import but you must download the audio to your device to play them. Reminders, tags, formatted text and note colors do not transfer (reminder notes will transfer - just not the actual Tasks)