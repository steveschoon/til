# VI Mode Command Editing

By default zsh uses EMACS editing mode.  To change to Vi mode:

`bindkey -v`.  

To switch back to Emacs 

`bindkey -e`

By default, Vi mode does not enable `CTRL-R` incremental command line history search.  To get that back use 

`bindkey "^R" history-incremental-search-backward`
