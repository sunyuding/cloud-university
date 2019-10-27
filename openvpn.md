# Open VPN
## Add VPN Access Manually
1. Create OpenVPN Users 
```bash
[root ~]# cd /etc/openvpn/easy-rsa/
[root easy-rsa]# source /etc/openvpn/easy-rsa/vars && /etc/openvpn/easy-rsa/pkitool <username>
NOTE: If you run ./clean-all, I will be doing a rm -rf on /etc/openvpn/keys
Generating a 1024 bit RSA private key
..........................................................................++++++
.....................................++++++
writing new private key to '<username>.key'
-----
Using configuration from /etc/openvpn/easy-rsa/openssl-1.0.0.cnf
Check that the request matches the signature
Signature ok
The Subject's Distinguished Name is as follows
countryName           :PRINTABLE:'US'
stateOrProvinceName   :PRINTABLE:'CA'
localityName          :PRINTABLE:'San Francisco'
organizationName      :PRINTABLE:'Insikt'
commonName            :PRINTABLE:'<username>'
emailAddress          :IA5STRING:'it@insikt.com'
Certificate is to be certified until Oct 14 23:49:39 2029 GMT (3650 days)

Write out database with 1 new entries
Data Base Updated
```
2. Update Key permissions
```
[root easy-rsa]# chmod 0700 /etc/openvpn/keys/<username>.key
```
3. Create ovpn file 

Copy a file to /etc/openvpn/keys/<username>.ovpn and modify the <username> inside
```
owner: root
group: root
mode: 0644
```
4. Create conf file
```
cp <username>.ovpn /etc/openvpn/keys/<username>.conf
```
5. Create Tar file

Under /etc/openvpn/keys
```
# tar -czf {{item}}.tar.gz {{item}}.conf {{item}}.crt {{item}}.key {{item}}.ovpn ca.crt
```
6. Copy Tar Files
```
# cp /etc/openvpn/keys/<username>.tar.gz /home/<username>/<username>.tar.gz
```
