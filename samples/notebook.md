
# Table of Contents

1.  [Keeping an Electronic Lab Notebook with Emacs Org Mode](#orgbc80b8c)
2.  [<span class="timestamp-wrapper"><span class="timestamp">&lt;31 Aug 2023&gt;</span></span> Title](#orgeea8eac):in_progress:
    1.  [Modified settings and variables for ELNs](#org94f1d8a)
        1.  [Change dates to display as 01 Jan 1970 with the month in characters](#org34ed6d9)
    2.  [Example Entry](#org71a7f14)
        1.  [<span class="timestamp-wrapper"><span class="timestamp">&lt; 1 Sep 2023&gt;</span></span> Getting the time in user space](#org141b11f):in_progress:


<a id="orgbc80b8c"></a>

# Keeping an Electronic Lab Notebook with Emacs Org Mode

Laboratory notebooks have a particular format and set of
requirements.  The first is to have proper dates, and titles for each
entry.  As such I have (for now) settled on the following format:


<a id="orgeea8eac"></a>

# EXPERIMENT <span class="timestamp-wrapper"><span class="timestamp">&lt;31 Aug 2023&gt;</span></span> Title     :in_progress:

Each entry starts with the state of the experiment (EXPERIMENT,
COMPLETE, FAILED) and then the date that the entry was added.  The
date has the month spelled out, to remove the whole
number/number/number ambiguity.  This is followed by the title because
the dates keep the formatting nicely static and don't produce a ragged
left edge.  Each experiment has a tag (not<sub>started</sub>, in<sub>progress</sub>,
complete) at the right edge (as dictated by org mode tag formatting).
The tags aren't necessary but are helpful to me in finding where I am
with many different experiments in a single notebook.

Work is clocked using org mode clock tables (see 3 lines following the
title) using C-c C-x C-i (clock in) and C-c C-x C-o (clock out).  When
an experiment is complete it is marked DONE and the clocks are
summarized.  At this point a discrete, signed, checkin is made to
complete the entry.


<a id="org94f1d8a"></a>

## Modified settings and variables for ELNs

The following changes are in my .emacs file for use with ELNs


<a id="org34ed6d9"></a>

### Change dates to display as 01 Jan 1970 with the month in characters

;; Setup an org mode custom date to match for ELNs

(setq-default org-display-custom-times t)
(setq org-time-stamp-custom-formats '("<%e %b %Y>" . "<%e %b %Y %H:%M>"))


<a id="org71a7f14"></a>

## Example Entry


<a id="org141b11f"></a>

### <span class="timestamp-wrapper"><span class="timestamp">&lt; 1 Sep 2023&gt;</span></span> Getting the time in user space     :in_progress:

1.  Hypothesis

    What are you trying to show?  Be specific about what you are
    measuring: time, transactions, size of data, latency etc.

2.  How

    (Procedures, calculations, equipment)
    
    -   The Details of How
    
    -   Equipment::CPU, Memory, Disk, Network features and base performance
        characteristics
    
    -   Software::Name, Version, Options
    
    -   Scaffolding Scripts, Executables::Location, name, command arguments
        passed
    
    -   Commands Typed:Use the script(1) command before you start any
        interactive session that will run test or other measurement code.
        This command captures all commands typed and their output for later
        use.

3.  Observations

    -   Describe all that happens (planned or unplanned) during the
        experiment in narrative text.
    
    -   Raw experimental data::Tables and other data that are small enough
        to fit directly into the notes may be place in this section.
    
    -   Large Output Files::Point to the files, signed and stored in a repo,
        that contain any relevant output.
    
    Org mode has a way to strike out text, C-c C-x C-f + which inserts
    plus mark characters that make a strikeout as in the following line:
    
    <del>- This idea did not work out and therefore is struck out.</del>
    
    In a Laboratory notebook we NEVER remove ideas, we leave them and
    strike them out.  Yes, we can recover text via the version control
    system but that's not suffiicent for our purpose, we need to have the
    strikeouts remain to work as a real lab notebook.

4.  Data analysis

    Processing of raw data, graphs, interpretations
    
    -   Summarize your interpretation of the results of the experiment in
        narrative text.
    
    -   Summary tables, graphs, images, etc. may be placed directly into the
        notes.
    
    -   Large Tables, Graphs, Images etc.::Point to the files, signed and
        stored in a repo, that contain any relevant output.

5.  Ideas for future experiments

    -   A list of further experiments that you believe that tease out new
        information.

