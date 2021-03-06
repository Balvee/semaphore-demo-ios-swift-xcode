# Signet

<dl>
  <dt>Homepage</dt><dd><a href="https://github.com/googleapis/signet/">https://github.com/googleapis/signet/</a></dd>
  <dt>Author</dt><dd><a href="mailto:bobaman@google.com">Bob Aman</a></dd>
  <dt>Copyright</dt><dd>Copyright © 2010 Google, Inc.</dd>
  <dt>License</dt><dd>Apache 2.0</dd>
</dl>

[![Gem Version](https://badge.fury.io/rb/signet.svg)](https://badge.fury.io/rb/signet)
[![Build Status](https://secure.travis-ci.org/google/signet.png)](http://travis-ci.org/google/signet)

## Description

Signet is an OAuth 1.0 / OAuth 2.0 implementation.

## Reference

- {Signet::OAuth1}
- {Signet::OAuth1::Client}
- {Signet::OAuth1::Credential}
- {Signet::OAuth1::Server}
- {Signet::OAuth2}
- {Signet::OAuth2::Client}

## Example Usage for Google

# Initialize the client

``` ruby
require 'signet/oauth_2/client'
client = Signet::OAuth2::Client.new(
  :authorization_uri => 'https://accounts.google.com/o/oauth2/auth',
  :token_credential_uri =>  'https://oauth2.googleapis.com/token',
  :client_id => '44410190108-74nkm6jc5e3vvjqis803frkvmu88cu3a.apps.googleusercontent.com',
  :client_secret => 'X1NUhvO-rQr9sm8uUSMY8i7v',
  :scope => 'email profile',
  :redirect_uri => 'https://example.client.com/oauth'
)
```

# Request an authorization code

```
redirect_to(client.authorization_uri)
```

# Obtain an access token

```
client.code = request.query['code']
client.fetch_access_token!
```

## Install

`gem install signet`

Be sure `https://rubygems.org` is in your gem sources.

## Supported Ruby Versions

This library requires Ruby 2.4 or later.
In general, this library supports Ruby versions that are considered current and
supported by Ruby Core (that is, Ruby versions that are either in normal
maintenance or in security maintenance).
See https://www.ruby-lang.org/en/downloads/branches/ for further details.
