# Python Script File, fmt/938

I don't think there is a definite and efficient way to identify a Python script
file in the context of PRONOM/DROID. The best approach for an internal signature
is probably to look for a [shebang
line](https://en.wikipedia.org/wiki/Shebang_(Unix)) at the BOF. This will not
always work out because some script files do not use a shebang or contain
comments or other content before it. So it is a matter of assessment, using no
internal signature at all (only extension) versus an internal signature that
matches in many but not all cases.

If you decide to use the shebang mechanism at least the following signatures
should be considered (all at BOF):

    #!/usr/bin/python → 23212F7573722F62696E2F707974686F6E
    #!/usr/local/bin/python → 23212F7573722F6C6F63616C2F62696E2F707974686F6E
    #!/usr/bin/env python → 23212F7573722F62696E2F656E7620707974686F6E

This also accounts for variants like `python3`.
