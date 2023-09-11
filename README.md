# Debug version to avoid compiling failure

## history

> lav2maf.c: line 18: "src1[500], src2[500]" to "src1[800], src2[800]"

```log
lav2maf.c:170:35: warning: ¡®%s¡¯ directive writing up to 499 bytes into a region of size between 300 and 499
lav2maf.c:170:35: warning: ¡®%s¡¯ directive writing up to 499 bytes into a region of size between 300 and 499
```

> mz_scores.h: line 8: "int" to "extern int"

> mz_scores.h: line 11: "int" to "extern int"

> mz_scores.c: line 7: add new line: "int gap_open, gap_extend;"

> mz_scores.c: line 8: add new line: "int **ss, *gop;;"

```
multiple definition of `ss'
multiple definition of `gop'
multiple definition of `gap_open'
multiple definition of `gap_extend'
```

# multiz
DNA multiple sequence aligner, official version from Penn State's Miller Lab

This is a nearly functionally equivalent copy of the tarball and documentation
for multiz that was posted at the Miller Lab website January 21, 2009,
`http://www.bx.psu.edu/miller_lab`.

The motivation for this repository is to provide an equivalent of that tarball
that can be installed by modern package managers.

The only functional change that has been made is that this version uses lastz
to generate the underlying pariwise alignments. The 2009 release used blastz
instead. Blastz has now been deprecated for nearly a decade, and lastz is a
drop-in replacement for it.

The only other changes are the addition of this README.md, the MIT license,
and several syntax changes to prevent compiler warnings.
