# modelestimator

## Description

This program estimates amino acid replacement rates from an input of
aligned sequences. The method is described in the paper mentioned
below ("Please cite").


## Availability

`modelestimator` is distributed under the GNU General Public License,
and is available for immediate download. This is version 1.1, which
improves on version 1.0 by fixing a bug regarding scaling of the rate
matrix and work on recent versions of Octave (cell arrays are used
instead of deprecated lists.) The software is a Perl script that reads
input, produces script files for, and pipes them to, Octave that does
the actual computations. A fairly recent version of Octave is needed
as the 'list' function must be supported.

Please cite

  * Lars Arvestad, Efficient methods for estimating amino acid replacement
rates, 2006, J Mol Evol, 62(6):663–673.

if you use modelestimator!


## Usage

```
Usage: modelestimator [<options>] <infile> [<outfile>]
```

The infile should be in either FASTA, STOCKHOLM, or PHYLIP format.
Output is a rate matrix and residue distribution vector, both in
Octave/Matlab format.

### Options

```
-indels        Remove gap columns. A gap is denoted by '-'.

-threshold <f> Stop when consecutive iterations do not change by more
               than <f>. Default is 0.001.

-paml          Output model for use with PAML.
-fasta         Output substitution matrix (Pam250) for use with FastA.

-v             Verbose. Show progress info on STDERR.
-octave <path> Point to the Octave binary to run. 'octave' by default.

-d             Debug option. Output Octave commands to STDOUT.

-version       Show version information.
-u, -h         This help text.
```
