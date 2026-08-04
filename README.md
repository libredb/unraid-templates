# LibreDB unraid-templates

Unraid Community Applications template for [LibreDB Studio](https://github.com/libredb/libredb-studio), an open source (MIT) self-hosted SQL IDE. This repository holds the store packaging only; the product source lives at [libredb/libredb-studio](https://github.com/libredb/libredb-studio).

- `templates/libredb-studio.xml` - the Community Applications Docker template
- `ca_profile.xml` - maintainer profile
- `icon.svg` - repository icon
- `icons/libredb-studio.png` - app icon used by the template

The app runs as a single container with an embedded SQLite settings store. Data is kept under `/mnt/user/appdata/libredb-studio` so it persists across updates.

## Setup notes

- Set `Admin Email`, `Admin Password`, and `JWT Secret` on first install. These are required; leave none of them blank or the app will not start.
- Keep the WebUI host port at the default (3006) or pick any free port other than 3000. Serving on host port 3000 breaks login.
