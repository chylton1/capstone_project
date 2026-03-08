# CITC Mobile App (Ionic v1 + Cordova + JSON Server)

This project is a mobile course catalog and advising app for CITC, built with Ionic v1/AngularJS and packaged with Cordova.

## Features

- Course catalog with category tabs
- Course detail pages with comments
- Favorites (saved in local storage)
- About/Faculty and Contact pages
- Login and advising reservation modals
- Mock REST backend using JSON Server

## Tech Stack

- Ionic v1
- AngularJS + `ngResource`
- Cordova (`cordova-android`)
- JSON Server (mock API)

## Project Structure

- `www/` - Ionic/AngularJS app (templates, controllers, services, assets)
- `json-server/` - mock backend (`db.json`) and static images
- `platforms/android/` - generated Android platform files
- `config.xml` - Cordova app config
- `package.json` - project dependencies

## Prerequisites

- Node.js + npm
- Android Studio + Android SDK + Emulator (AVD)
- Cordova CLI (or use `npx cordova`)

## Run Locally

### 1) Start mock backend

From project root:

```bat
npx json-server --watch json-server/db.json --static json-server/public --port 3000
```

If port `3000` is in use, use a different port (for example `3001`) and update `baseURL` in `www/js/services_courses.js`.

### 2) Start Android emulator

Use Android Studio Device Manager and start an AVD.

### 3) Run app on emulator

From project root:

```bat
cmd /c npx cordova run android
```

`cmd /c` is used to avoid PowerShell execution-policy issues with `npx.ps1`.

## API Base URL

Current base URL is configured in:

- `www/js/services_courses.js`

```js
.constant("baseURL","http://10.0.2.2:3000/")
```

`10.0.2.2` is the Android emulator alias for your host machine.

## Key App Files

- App module/routing: `www/js/app_courses.js`
- Services/factories: `www/js/services_courses.js`
- Controllers: `www/js/controllers_2_courses.js`
- Main entry: `www/index.html`
- Templates: `www/templates/`

## Notes

- This is a legacy Ionic v1/AngularJS codebase.
- `platforms/` is generated content and may vary per machine.

