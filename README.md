# search-replace-turbo
A simple shell script that significantly increases the speed of WP-CLI's search-replace command, leading to less downtime when moving WordPress sites.

## explain the secret sauce

I did a full report a while back on WP-CLI's own issues tracker you can read more indepth here, but the TLDR is WP-CLI is searching through SQL database columns that it will never find values to replace for. It is like trying to find a needle in a haystack that you know doesn't have a needle! As the database gets larger and more rows are stored the benefits of column skipping becomes way more apparent.

## explain the mode(s)
(SAFEST) v4 - focuses on the safest possible things to skip over column wise ONLY. This means integers, booleans, datetimes from WP Core and top 50 of the latest plugins.

## why not add this to wp-cli or as a plugin? 

I don't have the time to support WP-CLI in that way. I've done my due diligence by reporting it to [them](https://github.com/wp-cli/search-replace-command/issues/194), [as others have in the past as well](https://github.com/WordPress/data-liberation/discussions/74). WordPress is also a constantly changing software between major versions that makes it hard for me on my own to support a plugin version. This structure outside of all that keeps this compatbile for potentially many years to come without me.
