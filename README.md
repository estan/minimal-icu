# Windows Builds of ICU with Minimal Data

These are 32 and 64 bit builds of various versions of ICU using MSVC 2010 and
2013. The library is built on the [Appveyor CI][appveyor-ci]. Downloads are
available as ZIP files attached to [releases][releases] here at GitHub. Only
the `icudtXY.dll`, `icuinXY.dll`, `icuucXY.dll` are included. These are the
ones required when deploying Qt applications.

The ICU versions were picked to match those used by official Qt builds.

## Note to Self: Add New ICU Version

When a new version XY.Z of ICU is needed, do the following:

* Visit the [ICU Data Library Customizer][datacustom].
* Click link at the bottom for the new version.
* Uncheck all categories.
* Click "Get Data Library".
* Save XML sent in the POST request as `data_request_XY.xml`.
* Add entries for MSVC 2010 / 2013 to matrix in `appveyor.yml`.
* `git commit && git push`

The building of the test data may fail due to missing data files. If this
happens, add the missing files back in and try again.

[appveyor-ci]:
    https://ci.appveyor.com/project/estan/minimal-icu
    "minimal-icu at Appveyor CI"

[releases]:
    https://github.com/estan/minimal-icu/releases
    "Releases for download"

[datacustom]:
    http://apps.icu-project.org/datacustom/
    "ICU Data Library Customizer"
