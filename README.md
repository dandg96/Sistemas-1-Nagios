# Sistemas-1-Nagios

## Si tienes problemas al comprobar versión de NRPE en el equipo windows cliente:

1. Generate DH key on Linux machine (it takes a long time)

  `openssl dhparam -C 2048 2> /dev/null|sed -n '/BEGIN/,/END/p'`

2. Paste your DH key to newly created file C:\Program Files\NSClient++\security\nrpe_dh_2048.pem

3. Edit C:\Program Files\NSClient++\nsclient.ini:

  [/settings/NRPE/server]
  dh = ${certificate-path}/nrpe_dh_2048.pem
 
3. Restart NSClient++ service: `net stop nsc` and then `net start nscp`
