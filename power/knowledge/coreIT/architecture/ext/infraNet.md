- internet - interconnected (vs connected) networks of computers -> data sharing
- www - system built on top of internet, uses standardized protocols (http, html), browsers, hypertext documents, multi-media -> sharing & navigating more efficiently (web-like manner, indexed)
- osi  https://stackoverflow.com/questions/41986458/osi-layers-explained
	- data link (methods for physical devices) - network (ip for routers) 
	- transport - sockets - communication endpoint
		- tcp - reliable (3 way handshake), unicast
		- udp - fast, unicast, multicast, broadcast
			- rtp - transmit (session & presentation layer)
	- application: streaming ingest -> transcode -> delivery https://www.wowza.com/blog/streaming-protocols#streaming-protocol, https://www.reddit.com/r/learnprogramming/comments/xwjda4/comment/ir70vma/?utm_source=share&utm_medium=web2x&context=3
		- rtmp (flash), rtsp (ip camera) (control protocol)  (not supported in many players) --> transcode into http-based
		- http adaptive streaming (hls, dash) -- bitrate Mbps
		- srt, webrtc
		- http/s
			- TCP handshake (syn, syn-ack, ack) - certificate check SSL/TLS (certificate is signature signed by private keys of certificate authorities, browsers store public keys -> server return TLS version, cipher suite) - key exchange (RSA TLS <=1.2, DH  TSL 1.3) 
				- https://www.youtube.com/watch?v=j9QmMEWmcfo&t=3s
				- cryptography
					- symmetric
						- DES (64 bits), AES (128, 192, 256 bits)
					- asymmetric
						- RSA
						- signature DSA
					- Diffie-Hellman key exchange
		- websockets
- api
	- GraphQL - '*extra REST*' more complex, flexible, multiple teams
	- tRPC - '*simpler REST*', a single API endpoint that operates behind your api engine
	-  gRPC - framework from rpc concept, on Http/2, microservices
	- openAPI/swagger - specification for building api https://cloud.google.com/blog/products/api-management/understanding-grpc-openapi-and-rest-and-when-to-use-them
- patterns/techniques
	- server-sent event
	- polling
		- long polling
		- short polling
	- webhook
- architecture 
	-  responsibility
		- monolithic
		- modular (microservices, microkernel)
	- communication
		- request-response
		- event-driven