Instalar Proton VPN Free
==========================

En este Link esta el instructivo:

https://protonvpn.com/support/es-419/linux-vpn-setup

Para debian:

https://protonvpn.com/support/es-419/official-linux-vpn-debian

Este es el procedimiento para Debian::

	wget https://repo.protonvpn.com/debian/dists/stable/main/binary-all/protonvpn-stable-release_1.0.8_all.deb
	dpkg -i ./protonvpn-stable-release_1.0.8_all.deb && sudo apt update
	echo "0b14e71586b22e498eb20926c48c7b434b751149b1f2af9902ef1cfe6b03e180 protonvpn-stable-release_1.0.8_all.deb" | sha256sum --check -
	apt install proton-vpn-gnome-desktop

Debes registrarte en la pagina de Proton VPN.

Luego en Gnome busca: Proton VPN, colocas el usuario que registrate.

Y seleccionas en donde dice United States -> Connect

Para probar puede utilizar un whoami o buscar un error de ORA que sera un link de Oracle.
