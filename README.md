J'ai eu l'opportunité de réaliser une architecture réseau sur packet tracer (en mode physique et logique) visant à simuler des cas de production réels. Cette architecture reposait sur plusieurs composants clés : routage dynamique et statique, EtherChannel, services web, DHCP, DNS, routage inter-VLAN, VLANs et tunnel IPsec over GRE afin de garantir une connectivité fiable et sécurisée.

J'ai commencé par créer un LAN à Casablanca en utilisant une architecture 2-tiers Dans ce LAN, j'ai configuré quatre VLANs afin de séparer les services tout en assurant la redondance via des liens doubles et l'EtherChannel entre les switches L3. Ensuite, j'ai réalisé la même configuration à LAN Rabat, et la connexion entre les deux sites a été effectuée via un réseau ISP basé sur le routage OSPF. Pour établir une connexion point à point, un tunnel GRE a été configuré entre les deux sites. Cependant, comme ce tunnel n'était pas sécurisé, un tunnel IPsec a été mis en place pour chiffrer les communications, formant ainsi un réseau overlay.

Par la suite, pour continuer la simulation, le LAN du datacenter a été créé avec deux serveurs web simulant (facebook.com et google.com), ainsi qu'un serveur DNS.

La communication entre les différents LANs s'effectue à travers le réseau ISP, qui assure des liens redondants tout en se basant sur OSPF pour le routage
