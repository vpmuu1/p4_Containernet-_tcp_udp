# p4_Containernet-_tcp_udp
p4_Containernet _tcp_udp

basic l2 switch add tcp udp support


git clone https://github.com/ANTLab-polimi/FOP4

cd FOP4/P4_examples

git clone https://github.com/vpmuu1/p4_Containernet-_tcp_udp.git

cd p4_Containernet-_tcp_udp

p4c-bm2-ss --arch v1model -o basic.json   --p4runtime-file load_balancer_hash.p4info --p4runtime-format text  basic.p4

python3 basic.py

sh simple_switch_CLI --thrift-port $(cat /tmp/bmv2-s1-thrift-port) <cmd1.txt

pingall

xterm d1 d2

in d1 : nc -l 9999

in d2 : nc 192.168.1.202 9999

tcp or udp all work
 

