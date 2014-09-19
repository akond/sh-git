DOC = README.md

define HEAD =
sh-git
=========

My git speed dial functions


endef

.PHONY: $(DOC)
$(DOC):
	$(file >$@,$(HEAD))
	for i in `ls git-*`; do echo -n '* `'$$i'` - ' >> $@; (grep -oi "the motto:.*" $$i || echo "           No description yet") | cut -c 12-  >> $@;  done
