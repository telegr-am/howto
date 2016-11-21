# How to host a Telegram site on your domain

When you set up a Telegram site, it's hosted using the telegr.am domain by default.  But you may
want to host your own domain on your Telegram site.  It's a pretty easy process:

1. Set the domain in the "Edit Site" dialog ![dialog](/images/domain.png)
2. Set up a [CNAME record](http://en.wikipedia.org/wiki/CNAME_record) to point to `ssl_cname.telegr.am`
   at your DNS provider.

By default, you cannot use a root domain (e.g. `goodstuff.im`) to host a domain.
This is because [it breaks things to point a `CNAME` record at a root domain](http://serverfault.com/questions/91712/dns-using-cnames-breaks-mx-records).

## Using a root Domain

If you know what you're doing and want to use your root domain with Telegram:

1. Enable "Power User" mode for your account: ![power user](/images/edit_user.png)
2. Enter your root level domain in the "Optional Domain Name" field of the "Edit Site" dialog
3. Set up an `A` DNS record to point to `34.192.111.227`

## Wildcard domain support

We will enable wildcard Domain support for your Telegram site after verifying that you
own the domain you want to wildcard.  Please [email us](mailto:howdy@telegr.am) with
a request for wildcard support.

## Multiple domain support

Telegram's inner workings support multiple domains per site, but there's no web
interface for multiple domain support.  If you need multiple domain support, please
email us.

## Cost

Some services charge extra for custom domain support.  Telegram supports multiple
domains as part of the basic service.
