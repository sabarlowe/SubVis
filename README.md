# SubVis

#### Author:  
    Scott Barlowe

#### Description:  
    Software tool for visual analysis of substitution matrix effects on protein 
    sequence alignment.
    
#### Getting started (for Windows):
    1.  Install R Studio (R version  version 3.3.0 or later).
    2.  Install required R packages (and any dependencies):
            'shiny' 
            'Biostrings'
    3.  Download the SubVis folder (source code and test files).
    4.  Create a new SubVis project in RStudio by going to File --> New Project... --> Existing Directory
        and then selecting the SubVis directory.
    5.  From the command line, source ui.R with the source() command.
        Example:  source('C:/Users/sabarlowe/Desktop/SubVis/ui.R')
    6.  From the command line, execute the app with the runApp() command.
        This will launch the application.
        Example:  runApp('C:/Users/sabarlowe/Desktop/SubVis')

#### Layout
    After launching, there are two main tabs:  Options and Viz
    
##### The Options tab:  Loading data, matrices, and parameters
    1.  Protein sequences (one per file) must be in FASTA format.  There
        are two example FASTA files in the test folder.
    2.  BLOSUM and PAM matrices can be selected by checking the appropriate box.
    3.  A custom matrix in the form of the predefined matrices can be loaded from 
        a text file.  The basic form is 
            First row --> Characters representing lookup table.
            First col --> Transpose of first row startingat row 2
            All other entries are substitution values.
        An example (mymatrix.txt) is included in the test folder.
    4.  The extension penalty, gap penalty, and score type can be selected
        by text boxes and a drop-down menu.

    Note:  Each time a change in the options tab is made, the GO button (in the 
    Overview or detail view) must be clicked.

##### The Viz tab:  Overview and Detail view

###### Overview

    Each row (except the last) represents a percent identity type.  Within each row, the pid for
    the selected matrices are sorted.  The last row is the sorted overall score.  
    
    Interaction:  When the mouse moves over a matrix type, the corresponding matrix in the 
    other rows are identified.
    
    Interaction:  '+' enlarges the display and '-' shrinks the display.
    
###### Detail

    Score is located under the matrix type for each alignment pair.  Amino acids are represented by a color-coded
    box.
    
    Interaction:  Size
        1.  '+' enlarges the display.
        2.  '-' shrinks the display.
    
    Interaction:  Mouse over an amino acid.
        1.  Histogram showing the number of each amino acid in that column.
        2.  Log-odds score and the amino acid substitution displayed under the score for each alignment.
        3.  Amino acid, log-odds score, amino acid subsitution is shown in the top right
    
    Interaction: Classification
        1.  Classify amino acids according to minor adjustment of [1].
    
    Interaction: Nagivation
        1.  'Start' - Go to position 1.
        2.  'End' - Go to the end of the maximum alignment.
        3.  'Pair' - Show both the pattern and subject for each matrix type.
        4.  'Patt' - Show only the pattern for each matrix type.
        5.  'Subj' - Show only the subject for each matrix type.
        6.  'Up' - Scroll up if all matrix types will not fit onto display space.
        7.  'Dn' - Scroll down if all matrix types will not fit onto display space.
        8.  '<-' - Go backward in the alignment.
        9.  '->' - Go forward in the alignment.
        10. 'Alpha' - Show amino acid instead of boxes
        11. 'Pos' - Go to a position by entering column in text box. (Requires clicking 'Go')
        
    Interaction: Search (All require clicking 'Go')
        1.  'NONE' - No search function on (default).
        2.  'INDEL' - Shows the insertions and deletions in red.
        3.  'MATCH' - Shows the positions that match in both the pattern and subject.
        4.  'SEQ' - The amino acid to be searched for.
    
#### Notes:

    Most error checking is delegated to the individual R and Biostrings functions.
    

#### References:

    1.  Pages, H., Aboyoun, P., Gentleman, R., DebRoy, S.: Biostrings: String
        Objects Representing Biological Sequences, and Matching Algorithms.
        R package version 2.32.0
        
    2.  Pearson, W.R., Lipman, D.J.: Improved tools for biological sequence
        comparison. Proc. Natl. Acad. Sci. USA 85(8), 2444{2448 (1988)
        
    3.  Pommie, C., Levadoux, S., Sabatier, R., Lefranc, G., Lefranc, M.: Imgt
        standardized criteria for statistical analysis of immunoglobulin v-region
        amino acid properties. Journal of Molecular Recognition 17(1), 17{32
        (2004)
    
    4.  R Core Team: R: A Language and Environment for Statistical
        Computing. R Foundation for Statistical Computing, Vienna, Austria
        (2013). R Foundation for Statistical Computing.
        http://www.R-project.org/

    5.  RStudio, Inc.: Shiny: Web Application Framework for R. (2014). R
        package version 0.10.1. http://CRAN.R-project.org/package=shiny
