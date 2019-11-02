# Pleroma Emojo Stealer

For stealing emojo packs that aren't sharable. From any mastoapi-supporting
instance (that's pleroma/mastodon)

## Usage

List the emojo in use by an instance:

```bash
./list pleroma.site
```

you'll see a list of all emojo, along with their URL

the URLs will look like `https://pleroma.site/emoji/bunhd_flip/revbunhdcry.png
` - this form is `https://HOST/emoji/(custom/)?PACK/filename.png`

you want the `PACK` bit. In our example that'd be `bunhd_flip`

Alternatively you can just take a substring from there that identifies them all. if you want to steal all buns, you can just take `bun`

Then run `sudo -Hu pleroma ./steal pleroma.site bunhd_flip` and the emojo will be downloaded to your `/var/www/pleroma/priv/static/emoji/custom/PACK` directory.

As a more generic usage:

```bash
./list INSTANCE
  Returns a list of emojo along with their static URLs form INSTANCE

./steal INSTANCE SUBSTRING
  Downloads all emojo who's static_url contains SUBSTRING from INSTANCE
```
