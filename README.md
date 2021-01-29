Day 1 on my blog
I had been working with binary/hexdecimal data all the time. A day-to-day task is to strip a piece of data then decode it to a meaningful format. E.g. A parcel of IP would be like

Offsets Octet 0 1 2 3 Octet Bit 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 0 0 Version IHL DSCP ECN Total Length 4 32 Identification Flags Fragment Offset 8 64 Time To Live Protocol Header Checksum 12 96 Source IP Address 16 128 Destination IP Address 20 160 Options (if IHL > 5) 24 192 28 224 32 256 Version

Decoding a field from a parcel would be really painful. We had made some tools to speed up the case, but they are mostly one-time and of single purpose. Now I found this one scapy https://scapy.net which is almighty and is able to decode a lot of packet types: Automotive protocols, Bluetooth, HTTP, TCP and so on. For example: https://scapy.readthedocs.io/en/latest/layers/tcp.html

And here you will be able to add new layer of protocol https://scapy.readthedocs.io/en/latest/build_dissect.html

https://medium.com/datadriveninvestor/arp-cache-poisoning-using-scapy-d6711ecbe112 shows a good exmple of doing test with scapy.

Pretty enough, right? But we even have more here: https://gitlab.com/mike01/pypacker is showing a simliar but more joyful interface.
