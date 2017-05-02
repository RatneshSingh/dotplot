# dotplot
Perl script to draw dotplots from various types of comparison. Converts comparison results to graphics in the form of dotplot. Currenlty uses blast table, MSTMap, Linkage maps, or a regular table with information on matches.


###
```
Usage:
perl dotplot.pl (infile|lgtable|blastTable) -options..
Options:
    -infile|i           infile from mstmap result out
    -lgtable|lgt        lg table with 4 columns.If -lgt is not provided with -i, script assumes that marker names in mst output file includes this info as "MarkerName_Contig_number_location"
                        eg. MarkerName  ContigName      LocationOnContig        LinkageGroup    locationOnLG
    -dagchainer_table|dt result produced by dagchainer.
    ********************************************************************
    -blast_table|bt     blast result in table format.
    -fil_alen|fal       only plot hits of this alignment length or higher
    -fil_eval|fev       only plot hits of this evalue or lower
    -fil_pid|fpi        only plot hits of this percent identity or higher

    -fill_name|fnm      only hits with this string as part of name in query or subject.
    -fil_qname|fqn      only hits with this string as part of name in query.
    -fil_sname|fqs      only hits with this string as part of name in subject.
    -exact              select exact matches instead of pattern match

    -resolution|res     resolution thrshold in nt to draw multiple dots if alignment is longer than resolution[10000]
    -keep_same_order|kso Keep the order of contigs on y and x axis same. Use it only when using blast result to self.
                        This opton will keep the broken diagonal to minimum when dot plot to self is plotted.
    -keep_same_scale|ksc  Keep scale of drawing on both axis same. Usefull when both axis are drawing sequences
                        and user want to keep the aspect ratios of lengths.
    ********************************************************************
    -reg_table|rt       Regular table with 4col of info,
    -seq1               column containing Sequence1 Name  [1]
    -loc1               column Sequence1   Match Location [2]
    -seq2               column containing Sequence2 Name  [3]
    -loc2               column Sequence2   Match Location [4]
    ********************************************************************
    -referencex|rfx     reference genome fasta file to get size for x axis.
    -referencey|rfy     reference genome fasta file to get size for y axis.
    -refseqlenx|rflx    file for x axis containing reference sequence length as seqName Length.
    -refseqleny|rfly    file for y axis containing reference sequence length as seqName Length.
    ********************************************************************
    -out|o              outfile [infile.png ]
    -print_list|pl      print the list of names showing homology
    -img_width|iw       img_width [ 1200 ]
    -img_height|ih      img_height [ 600 ]
    -lg_top|lt          lg_top [ 100 ]
    -cont_top|ct        cont_top [ 100 ]
    -margin|m           margin [ 100 ]
    -font_size|fs       font_size [ 10 ]
    -dotsize|ds         dotsize [ 3 ]
    -no_grid_lines|ngl  no_grid_lines
    -zoom_on_hits|zh    zoom plotting on the hit regions only.
    -equal_block|eb     assigne equal block for each query/subject irrespective of their size.
                        each entry will not on scale to each other.
    -verbose|v          verbose
    -svg                print image as svg. could not make it to print text.Only dotplot.

    ## order names on axis [default ordering is by size]
    -order_by_size|obs  order_by_size [default],
    -order_by_alpha|oba  order_by_alpha,
    -order_by_number|obn  order_by_num. order only by numbers in the names.
    -order_by_homology|olg  order_by_homology,
    -user_defined_order_x|udox user defined order on X axis from a file
    -user_defined_order_y|udoy user defined order on Y axis from a file
    -rotate_x_label|rxl rotate x axis labels [-90]
    -rotate_y_label|ryl rotate y axis labels [0]
    -rotate_xy_label|rxyl rotate xy axis labels
    -scale_x|scx  Add scale on x-axis (cannot be used with zoomed hits option)
    -scale_x_dist|dscx use provided scale for x axis
    -scale_y|scy  Add scale on y-axis (cannot be used with zoomed hits option)
    -scale_y_dist|dscy use provided scale for y axis
    -switch_axis|swa    switch_axis
    -order_by_lg|olg    order contigs based on similarity to lgs.
    -min_markers|mm     Minimum numbe of markers to present for a contig to be aligned on LG
    -as_marker|am       Use user provided char as marker for dotplot.eg. x
    -no_file_name|nfn   Dont print the outfilename at the bottom of  figure.
    -help|h             help

```
