LINK_PATH=$(HOME)/.i3
CONF_PATH=$(CURDIR)
BLOCK_CONTRIB_URL=https://github.com/vivien/i3blocks-contrib.git

BLOCKS_LINK_PATH=$(HOME)/.i3blocks.conf
BLOCKS_CONF_PATH=$(CURDIR)/i3blocks.conf

.PHONY: install uninstall

install:
	$(RM) -r $(LINK_PATH) && ln -sf $(CONF_PATH) $(LINK_PATH)
	$(RM) -r $(BLOCKS_LINK_PATH) && ln -sf $(BLOCKS_CONF_PATH) $(BLOCKS_LINK_PATH)
	$(RM) -r $(CURDIR)/i3blocks-contrib && git clone $(BLOCK_CONTRIB_URL) i3blocks-contrib

uninstall:
	test -h $(LINK_PATH) && test $(CONF_PATH) = `readlink $(LINK_PATH)` && $(RM) $(LINK_PATH) || :
	test -h $(BLOCKS_LINK_PATH) && test $(BLOCKS_CONF_PATH) = `readlink $(BLOCKS_LINK_PATH)` && $(RM) $(BLOCKS_LINK_PATH) || :
