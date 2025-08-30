Usando NetworkManager para hacer HotSpot(Recomendado)
==========================================================

1. Instalar NetworkManager (si no está instalado)
----------------------------------------------------
::

	sudo apt update
	sudo apt install network-manager
	
2. Crear hotspot con nmcli
-----------------------------

Crear un hotspot::

	sudo nmcli dev wifi hotspot ifname wlan0 ssid "MiDebianHotspot" password "micontraseña"

Verificar el estado::

	nmcli connection show

Si falla, configurar manualmente
--------------------------------
::

	# Eliminar conexión existente si hay
	nmcli connection delete "MiDebianHotspot" 2>/dev/null

	# Crear conexión de hotspot manualmente
	nmcli connection add type wifi ifname wlx488f4cff32ac con-name "MiHotspot" autoconnect no ssid "MiDebianHotspot"
	nmcli connection modify "MiHotspot" 802-11-wireless.mode ap
	nmcli connection modify "MiHotspot" 802-11-wireless.band bg
	nmcli connection modify "MiHotspot" ipv4.method shared
	nmcli connection modify "MiHotspot" ipv4.addresses 192.168.100.1/24
	nmcli connection modify "MiHotspot" wifi-sec.key-mgmt wpa-psk
	nmcli connection modify "MiHotspot" wifi-sec.proto rsn
	nmcli connection modify "MiHotspot" wifi-sec.group ccmp
	nmcli connection modify "MiHotspot" wifi-sec.pairwise ccmp
	nmcli connection modify "MiHotspot" wifi-sec.psk "Venezuela21"

	# Activar el hotspot
	nmcli connection up "MiHotspot"

