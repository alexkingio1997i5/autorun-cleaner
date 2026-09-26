# autorun-cleaner

I got tired of manually deleting 10-second pocket recordings, mucking about with stationary trainer rides that didn't record power, and manually muting my daily bike commutes so they don't clog my friends' feeds. This is a simple CLI utility that connects to the Strava API, checks your recent activities, and automatically cleans them up based on a set of simple rules.

I run this as a daily scheduled task on my Windows box.

## Setup

1. Create an API application on [Strava API Settings](https://www.strava.com/settings/api). Set the Authorization Callback Domain to `localhost`.
2. Copy `config.json.template` to `%USERPROFILE%\.autorun-cleaner.json` and fill in your client ID, client secret, and initial refresh token. 
3. Run the auth flow once to authorize access.

## Installation

```cmd
pip install -r requirements.txt
```

## Usage

Authorize the application to get your initial tokens:

```cmd
python cleaner.py auth --port 8080
```

Run the cleanup process using your local configuration rules:

```cmd
python cleaner.py run --rules rules.json
```

To make it run automatically, register `cleaner.py` in the Windows Task Scheduler to run daily.

<!-- last-checked: 2026-09-26 -->
