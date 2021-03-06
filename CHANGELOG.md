# IPInfo Changelog

## 3.0.0

#### Breaking Changes

- [PR #19](https://github.com/ipinfo/python/pull/19)
  DefaultCache requires keyword arguments now instead of positional arguments,
  in particular `maxsize` and `ttl`.

#### Bug Fix

- [PR #19](https://github.com/ipinfo/python/pull/19)
  [Issue #18](https://github.com/ipinfo/python/issues/18)
  An issue with the handler not being created if you provide your own custom
  `maxsize`/`ttl` values has been fixed.

## 2.1.0

#### General

- Released a batch ops function on the handler called `getBatchDetails` which
  accepts a list of IP addresses (or an IP address plus a path to more specific
  details, e.g. `8.8.8.8/country`). See documentation on batch operations in the
  README for more details.

## 2.0.0

#### Breaking Changes

- Fix [Issue #8](https://github.com/ipinfo/python/issues/8).
  Deleted the `ip_address` key in the details object which was of type [`IPv4Address`](https://docs.python.org/3/library/ipaddress.html).

  This allows serializing the details object (into JSON or something else) without errors by default.

  Users who expected that object type can simply pull the `ip` key instead and turn it into an [`IPv4Address`](https://docs.python.org/3/library/ipaddress.html)
  object on their own.
