
`echo "6" | seq `cat` -1 1 | cat -n | gawk '{print $1+$2-1}'`
