Purpose
=======

The purpose of the idn-properties tool is to list a summary
of the codepoints in the provided file. Input files can be
formatted as RFC 4290 tables, RFC 3743, or just any text file
containing a table of Unicode codepoints in the format of
U+[A-Z]+.

Output
------

The output is a summary of scripts being used, and a summary
of the derived properties as concluded by the IDNA2008 algorithms.
(PVALID, DISALLOWED and so on.)

Example output:

    $> idn-properties --file example-tables/se-yiddish.txt
    Reading allcodepoints.txt
    Reading Scripts.txt

    example-tables/se-yiddish.txt (PASS)
     # Properties
       PVALID: 45
     # Scripts
       Common: 11
       Hebrew: 34

A complete extended table with the derived and script properties
can be output using the --report file option.

    $> idn-properties --files example-tables/* --reportDir reports
    Reading allcodepoints.txt
    Reading Scripts.txt

    example-tables/se-latin.txt (PASS)
     # Properties
       PVALID: 131
     # Scripts
       Common: 11
       Latin: 120
    reports/example-tables/se-latin.txt written

    example-tables/se-sv.txt (PASS)
     # Properties
       PVALID: 42
     # Scripts
       Common: 11
       Latin: 31
    reports/example-tables/se-sv.txt written

    example-tables/se-yiddish.txt (PASS)
     # Properties
       PVALID: 45
     # Scripts
       Common: 11
       Hebrew: 34
    reports/example-tables/se-yiddish.txt written


Testing based on
----------------

All testing is done based on Unicode 6.2 and IDNA2008.

The table codepoints.txt was generated with the ruby program createtables
found here: http://stupid.domain.name/idna
(Thanks to Patrik Fältström)

The Unicode source files can be found here:
http://www.unicode.org/Public/6.2.0/ucd/

The Unicode Script file can be found here:
http://www.unicode.org/Public/6.2.0/ucd/Scripts.txt

/ Patrik Wallström, pawal@iis.se
