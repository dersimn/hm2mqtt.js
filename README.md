# hm2mqtt.js

#### History of this project

It started off with owagner's Java-based [hm2mqtt](https://github.com/owagner/hm2mqtt). Hobbyquaker then created [hm2mqtt.js](https://github.com/hobbyquaker/hm2mqtt.js) (JavaScript) providing the same functionality as hm2mqtt. He gave up the development in favor his new projects [node-red-contrib-ccu](https://github.com/hobbyquaker/node-red-contrib-ccu) and [RedMatic](https://github.com/hobbyquaker/RedMatic).

I forked the project some time ago and added a few features to it. This project however got a bit too inflated for my taste, thus I'm also working on a very simple approach, implementing only rfd. No rega, no paramset database, just sending and receiving messages: [simple homematic rfd](https://github.com/dersimn/simplehomematicrfd2mqtt).


## Usage with Docker

Run

	docker run dersimn/hm2mqtt.js --help

for a full list of options. A full command could look like this:

	docker run -d --restart=always --name=hm \
		-p 2126:2126 -p 2127:2127 \
		dersimn/hm2mqtt.js \
		--mqtt-url mqtt://10.1.1.50 \
		--ccu-address 10.1.1.112 \
		--disable-rega \
		--init-address 10.1.1.50 \
		--protocol-prefer-strings \
		--protocol-disable-value-checking \
		--protocol-publish-enum-as-string \
		--protocol-prefer-xmlrpc-for-rfd


## License

MIT (c) 2017 [Sebastian Raff](https://github.com/hobbyquaker)
