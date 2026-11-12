# Birdsong add-on for Home Assistant

[Birdsong](https://github.com/dopeytree/birdsong) draws the birds a BirdNET-Go
station has heard as one plate of 1800s illustrations. This repository runs it
as a Home Assistant add-on, in the sidebar.

## Install

1. Settings → Add-ons → Add-on Store → ⋮ → Repositories, and add
   `https://github.com/onetxpanda/ha-birdsong`.
2. Install **Birdsong**, start it, and open it from the sidebar.

It reads BirdNET-Go at `http://db21ed7f-birdnet-go:8080` (the Birdnet-go
add-on) unless `birdnet_url` says otherwise. See
[birdsong/DOCS.md](birdsong/DOCS.md).

## License

The add-on files are MIT. Birdsong is MIT, its bird artwork CC BY-SA 4.0
(Fugleramme); see the Birdsong repository.
