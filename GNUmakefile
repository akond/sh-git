DOC = README.md

.PHONY: $(DOC)
$(DOC):
	git remote -v | head -n 1 | egrep -o akond/[^[:space:]]+ | cut -c 7- > $@
	echo "=========" >> $@
	echo >> $@
	echo >> $@
	echo "My git speed dial functions" >> $@
	echo >> $@
	for i in `ls git-*`; do echo -n '* `'$$i'` - ' >> $@; (grep -oi "the motto:.*" $$i || echo "           No description yet") | cut -c 12-  >> $@;  done
	
	
	
