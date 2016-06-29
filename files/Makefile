proxy.cfg: global.cfg default.cfg frontend.d/*.cfg backend.d/*.cfg
	cat $^ > $@

clean:
	rm haproxy.cfg
