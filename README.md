# Spotipy

##### A light weight Python library for the Spotify Web API

![Tests](https://github.com/plamere/spotipy/workflows/Tests/badge.svg?branch=master) [![Documentation Status](https://readthedocs.org/projects/spotipy/badge/?version=latest)](https://spotipy.readthedocs.io/en/latest/?badge=latest)

## Documentation

Spotipy's full documentation is online at [Spotipy Documentation](http://spotipy.readthedocs.org/).

## Installation

A full tutorial on how to set up and use Spotipy can be found [here](https://github.com/davoodalavi/spotipy/blob/master/TUTORIAL.md)

```bash
pip install spotipy
```

alternatively, for Windows users not using bash

```bash
py -m pip install spotipy
```

if you have installed and need to upgrade

```bash
pip install spotipy --upgrade
```

## Quick Start

A full set of examples can be found in the [online documentation](http://spotipy.readthedocs.org/) and in the [Spotipy examples directory](https://github.com/plamere/spotipy/tree/master/examples).

To get started, install spotipy and create an app on https://developers.spotify.com/.

  1. Select "Login" from the top right-hand corner
  ![image](https://github.com/davoodalavi/spotipy/assets/22606346/de634730-eab2-46d4-ad74-2fe8e87ddf8f)
   
  
  2. Click on your account in the top right-hand corner and navigate to dashboard.
  ![image](https://github.com/davoodalavi/spotipy/assets/22606346/57b597c3-5fc3-4c3d-8395-bd26b3d58ac3)

  3. Create a new App.
  ![image](https://github.com/davoodalavi/spotipy/assets/22606346/4d854259-0931-4a91-b616-3d963629d699)

  4. For redirect URI set it to localhost:3000 or some other port.
  ![image](https://github.com/davoodalavi/spotipy/assets/22606346/9015bd6d-fd47-4004-8a9e-60a30a8da874)


Add your new ID and SECRET to your environment:

This can be found by navigating to the settings of your app.

### With user authentication

A redirect URI must be added to your application at [My Dashboard](https://developer.spotify.com/dashboard/applications) to access user authenticated features.

```python
import spotipy
from spotipy.oauth2 import SpotifyOAuth

sp = spotipy.Spotify(auth_manager=SpotifyOAuth(client_id="YOUR_APP_CLIENT_ID",
                                               client_secret="YOUR_APP_CLIENT_SECRET",
                                               redirect_uri="YOUR_APP_REDIRECT_URI",
                                               scope="user-library-read"))

results = sp.current_user_saved_tracks()
for idx, item in enumerate(results['items']):
    track = item['track']
    print(idx, track['artists'][0]['name'], " – ", track['name'])
```

## Reporting Issues

For common questions please check our [FAQ](FAQ.md).

You can ask questions about Spotipy on
[Stack Overflow](http://stackoverflow.com/questions/ask).
Don’t forget to add the *Spotipy* tag, and any other relevant tags as well, before posting.

If you have suggestions, bugs or other issues specific to this library,
file them [here](https://github.com/plamere/spotipy/issues).
Or just send a pull request.
