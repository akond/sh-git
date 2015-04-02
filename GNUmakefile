DOC = README.md
MD = Markdown.pl

define HEAD =
sh-git
=========

My git speed dial functions


endef

.PHONY: $(DOC)
$(DOC): body
	$(file >$@,$(HEAD))
	egrep -v "^>[[:space:]]*$$" body >> $@

index.html: $(DOC)
	$(MD) $< > $@

see:
	@while inotifywait -e modify git-*; do \
	$(MAKE) index.html; firefox index.html; \
	done


.INTERMEDIATE: body

body:
	for i in `ls git-*`; do \
	echo -n '* `'$$i'` - ' >> $@; \
	(grep -oi "the motto:.*" $$i || echo "           No description yet") | cut -c 12-  >> $@;  \
	echo -n "> " >> $@; \
	(grep -oi "description:.*" $$i || echo "") | cut -c 13-  >> $@;  \
	echo >> $@; \
	done
