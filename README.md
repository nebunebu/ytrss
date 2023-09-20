# ytrss

This script scrapes an invidious instance to get upload history of a YouTube channel in xml format.
The RSS feeds for YouTube channels are limited to 15 initial entries and the official YouTube
API is limited to 50. This script does not have such limits.

## Demo
![Demo](./assets/ytrss.webm)

## Warnings
- This script is not Posix complaint.
- It is hardcoded to work with newsboat.

## DEPENDENCIES
- bash
- jq
- sed
- newsboat

## USE

1. Make the script executable
```sh
chmod +x ytrss
```
2. Put the script on your $PATH
```sh
mv ytrss ~/.local/bin/
```
3. Set a keybind in newsboat
```conf
macro f set browser "ytrss"; open-in-browser; set browser default
```
4. When hovering over, a feed for a youtube channel, press your macro key
then the macro you set in (3.). The script will create and link the xml
for that channels upload history.

5. Close and reopen newsboat. You should now see the feed for that
channel's upload history.

## Note

The dates in the <published> field of the xml are inaccurate and used so
that newsboat reads the entries in correct order.
