#Processing

## downloading

The files were created by commands of the form:
```
getpapers -q "(('forest plot') AND (stata) AND NOT (spss))" -x -p -k 100 -o stata
```
selecting papers containing `forest plot` and `stata` but not `spss`. This has a number of false postives, including papers on forests.

The opposite command

```

getpapers -q "(('forest plot') AND (spss) AND NOT (stata))" -x -p -k 100 -o spss
```
was much messier (not sure why).

## project /cTrees
The files are already in `cproject` format. The command for `stata` 
```
ami-makeproject -p stata --rawfiletypes 'xml,pdf'
``` 
is unnecessary. `spss` would be similar.

## converting PDFs
The PDFs were converted into SVG and PNGs. For `stata` (run from directory `forestplots`)
```
ami-pdf -p stata 
```
will split the files into `pdfimages/` and `svg/`.

## editing

The files were manually edited to 

* exclude papers without Forest Plots
* then exclude images which are not forest plots.
