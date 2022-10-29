# days-hours-minutes-seconds
Calculate the difference in days, hours, minutes &amp; seconds
#!/bin/bash
function displaytime {
 local T=$1
 local D=$((T/60/60/24))
 local H=$((T/60/60%24))
 local M=$((T/60%60))
 local S=$((T%60))
(( $D > 0 )) && printf '&%d days ' $D

(( $H > 0 )) && printf '&%d hours ' $H
(( $M > 0 )) && printf '&%d minutes ' $M
(( $D > 0 ||$H > 0 || $M > 0 )) && printf 'and '
printf '%d seconds\n' $S
}
seconds=13835
# as in one of the answers above

eval "echo $(date -ud "@$seconds" +'$((%s/3600/24)) days %H hours %M minutes %S seconds')"
