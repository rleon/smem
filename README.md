smem - analyzing system memory tool
===================================

*smem* is a tool that can give numerous reports on memory usage on Linux systems. Unlike existing tools, smem can report proportional set size (PSS), which is a more meaningful representation of the amount of memory used by libraries and applications in a virtual memory system.

Because large portions of physical memory are typically shared among multiple applications, the standard measure of memory usage known as resident set size (RSS) will significantly overestimate memory usage. PSS instead measures each application's "fair share" of each shared area to give a realistic measure.

smem has many features:
* system overview listing
* listings by process, mapping, user
* filtering by process, mapping, or user
* configurable columns from multiple data sources
* configurable output units and percentages
* configurable headers and totals
* reading live data from /proc
* reading data snapshots from directory mirrors or compressed tarballs
* lightweight capture tool for embedded systems
* built-in chart generation 

smem has a few requirements:
* a reasonably modern kernel (> 2.6.27 or so)
* a reasonably recent version of Python (2.4 or so)
* the matplotlib library for chart generation (optional, auto-detected) 

###Using smem###
* Show basic process information 	smem
* Show library-oriented view 	smem -m
* Show user-oriented view 	smem -u
* Show system view 	smem -R 4G -K /path/to/vmlinux -w
* Show totals and percentages 	smem -t -p
* Show different columns 	smem -c "name user pss"
* Sort by reverse RSS 	smem -s rss -r
* Show processes filtered by mapping 	smem -M libxml
* Show mappings filtered by process 	smem -m -P [e]volution
* Read data from capture tarball 	smem --source capture.tar.gz
* Show a bar chart labeled by pid 	smem --bar pid -c "pss uss"
* Show a pie chart of RSS labeled by name 	smem --pie name -s rss
