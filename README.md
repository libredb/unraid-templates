# LibreDB unraid-templates

Unraid Community Applications template for [LibreDB Studio](https://github.com/libredb/libredb-studio), an open source (MIT) self-hosted SQL IDE. This repository holds the store packaging only; the product source lives at [libredb/libredb-studio](https://github.com/libredb/libredb-studio).

- `templates/libredb-studio.xml` - the Community Applications Docker template
- `ca_profile.xml` - maintainer profile
- `icon.svg` - repository icon
- `icons/libredb-studio.png` - app icon used by the template

The app runs as a single container with an embedded SQLite settings store. Data is kept under `/mnt/user/appdata/libredb-studio` so it persists across updates.

## Setup notes

- The template asks for `Admin Email`, `Admin Password`, and `JWT Secret` on first install, and Unraid marks all three required, so fill them in. `JWT Secret` must be at least 32 characters. A shorter one stops the container at startup with a message saying so, because every login would otherwise fail. The app can generate the password and the secret itself when they are left unset, but this template always supplies them, so that path is not used here.
- Keep the WebUI host port at the default (3006), or pick any other free port. The template steers away from 3000 only because it commonly collides with other apps.
