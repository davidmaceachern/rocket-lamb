# Changelog

## [0.6.0] - 2019-09-01
### Added:
- `ResponseType::Auto` added as the default. If a response body is not valid UTF-8 then it will automatically get base-64 encoded.

## [0.5.0] - 2019-09-01
### Breaking Changes:
- The `include_api_gateway_base_path` method on `RockerHandlerBuilder` has been changed to `base_path_behaviour`. It should now detect the base path on API Gateway custom domains, as well as when using the default API Gateway URL.

## [0.4.0] - 2019-08-23
### Breaking Changes:
- Renamed `RocketLamb` to `RockerHandlerBuilder`
- The `launch` (and `into_handler`) methods on `RocketLamb`/`RockerHandlerBuilder` no longer return errors. Misconfigurations that prevent the handler from starting will now panic instead.

### Added:
- The handler will now try to detect the API Gateway base path for your lambda, and prepend this to the path processed by Rocket. This is necessary to make absolute URLs in responses (e.g. in the Location response header for redirects) function correctly when hosting the server at the default API Gateway URL. If this behaviour is unneeded or undesired, you can disable it with the `include_api_gateway_base_path` method on `RockerHandlerBuilder`.

## [0.3.1] - 2019-07-30
- Documentation changes only

## [0.3.0] - 2019-07-30
- Initial "public" release!
