# 🥰Jaringan lab komputer dibagi menjadi tiga VLAN (siswa, guru, dan server) supaya traffic 🥰
masing-masing kelompok terpisah. Port switch yang dipakai komputer diamankan dengan
port security sehingga hanya perangkat yang sudah terdaftar yang bisa memakai port
tersebut. Antar VLAN dihubungkan oleh router dengan metode router-on-a-stick.


# 🧨perangkat yang digunakan 🧨
# Cisco Packet Tracer 👩‍⚖️
# Port Security 🧒
# Vlan 👶
# Topologi 🥱🥱
<img width="547" height="349" alt="Topologi" src="https://github.com/user-attachments/assets/744b2377-6129-45d1-a860-c27603b2454a" />

# Cara Testing Apa Yang Sudah Kita Konfig 🎉🎉🎉🎉
jangan lupa pertama tama kita masukkan konfigurasi di setiap perangkat (cisco,router), jika sudah di konfig kalian harus mengeceknya satu persatu PAHAMMM!!🤯🤯🤯🤯🤯, dan jika kalian sudah mengeceknya satu persatu dan benar baru kalian ping satu sama lain 

# Konfigurasi notes 📝📝📝
[r1.txt](https://github.com/user-attachments/files/35446753/r1.txt)
enable
configure terminal
hostname R-LAB
interface gigabitEthernet 0/0
 no shutdown
exit
interface FastEthernet 0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
exit
interface  FastEthernet 0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
exit
interface  FastEthernet 0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.1 255.255.255.0
exit
end
write memo


[switch (1).txt](https://github.com/user-attachments/files/35446778/switch.1.txt)
enable
configure terminal
hostname SW-LAB
no ip domain-lookup
vlan 10
 name SISWA
vlan 20
 name GURU
vlan 30
 name SERVER
exit
interface range fastEthernet 0/1 - 3
 switchport mode access
 switchport access vlan 10
 switchport port-security
 switchport port-security maximum 1
 switchport port-security mac-address sticky
 switchport port-security violation shutdown
exit
interface fastEthernet 0/4
 switchport mode access
 switchport access vlan 20
 switchport port-security
 switchport port-security maximum 1
 switchport port-security mac-address sticky
 switchport port-security violation shutdown
exit
interface fastEthernet 0/5
 switchport mode access
 switchport access vlan 30
 switchport port-security
 switchport port-security maximum 1
 switchport port-security mac-address sticky
 switchport port-security violation shutdown
exit
interface fastEthernet 0/6
 switchport mode trunk
exit
end
write 

# Menutup
sekian terimakasih saya sandi.firdaus izin pamit bukan karena kalah,tapi saya tau kapan harus berhenti mendaur ulang sampah
<img width="386" height="518" alt="image" src="https://github.com/user-attachments/assets/46215a95-3791-48f8-8772-402ce94584af" />
