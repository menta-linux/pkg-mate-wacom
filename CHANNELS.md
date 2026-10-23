# Debian build channels

The workflow builds and archives all three channels on each packaging change and
on its six-hour schedule:

| Channel | Debian suite | Source selection | Version example |
| --- | --- | --- | --- |
| Nightly | Sid (`unstable`) | `HEAD` | `1.0.0+git20261022074500.abcdef0-1` |
| Testing | Forky | newest source tag, including RC tags | `1.0.0~rc1-1~deb14` |
| Stable | Trixie | newest final source tag | `1.0.0-1~deb13` |

Every artifact gets a GitHub Release in `menta-linux/pkg-mate-wacom`. Releases
are named `build/<channel>/<suite>/<source-key>-<revision>`. The distribution
manifest chooses the archived artifact to publish; stable is not pinned here.

For a source tag, the first artifact revision is `-1`. A change to the source
commit or to this packaging repository produces the next revision (`-2`, `-3`,
and so on). Re-running an unchanged source and packaging commit does nothing.

Testing accepts the workflow's optional `source_tag` input for a specific RC or
final tag. Source tags ending in `-rcN`, `.rcN`, `-betaN`, `.betaN`, `-alphaN`,
or `.alphaN` become Debian prerelease versions such as `1.0.0~rcN`.
