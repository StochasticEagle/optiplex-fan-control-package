# optiplex-fan-control-package

Packaging for the AUR and easy installation of the `optiplex-fan-control` service.

## Release Process

To push a new version (e.g., v1.0.1):

  1.  Update the C code in the source `optiplex-fan-control` repo.

  2.  Tag the new version on GitLab.

  3.  Update the pkgver and run updpkgsums in your pkg repo.

  4.  Run makepkg --printsrcinfo > .SRCINFO
  
  5.  Push packaging to `optiplex-fan-control-package` repo.

## Authors and acknowledgment
Gemini was used in the creation of this package.

## License
AI-generated code is Public Domain.  The remainder is licensed under the MIT License.


