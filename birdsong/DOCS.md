# Birdsong

Shows the birds a BirdNET-Go station has heard as one plate of hand-cut
1800s illustrations, each bird sized by how often it called, with a card per
bird (recent calls, recordings and spectrograms when BirdNET-Go keeps clips).
The page is [Birdsong](https://github.com/dopeytree/birdsong) by Ed Stone.

## Use

1. Install and start the add-on.
2. Open **Birdsong** in the sidebar.

## Options

- `birdnet_url`: BirdNET-Go's address as this add-on reaches it. The default,
  `http://db21ed7f-birdnet-go:8080`, is the Birdnet-go add-on from
  alexbelgium's repository. For a BirdNET-Go elsewhere, give its address, e.g.
  `http://192.168.1.50:8080`. If BirdNET-Go asks for a login, allow this
  add-on's address in its security settings.

To open the page outside Home Assistant, set a port for `80/tcp` under
Network. That address has no login.

## How it works

The add-on runs the Birdsong image unchanged except for one line: the page's
BirdNET-Go address defaults to `.`, so its requests stay relative to the page
and work under Home Assistant's add-on path. nginx in the container serves the
page and forwards `/api/` to `birdnet_url`. The page also fetches bird
descriptions from Wikipedia and some plates from Wikimedia Commons.
