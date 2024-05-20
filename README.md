№1 Имена: HQBR-R conf – hostname (Имя) – com - con; HQBR-SRVCLI (СLI) hostnamectl set-hostname (Имя) – exec bash
ip-адресация: CLI параметры соединения - ipV4 – вручную – вводим ip, маску, шлюз(ISP-CLI), DNS (8.8.8.8)
                           HQBR-R: Conf – int gi (1/0/12) – ip add (1.1.1.2/30) – ip firewall disable – com – con   
                           BR-SRV: echo (172.16.100.2/28) > /etc/net/ifaces/ens192/ipv4address – 
                                          еcho via default (172.16.100.1) > /etc/net/ifaces/ens192/ipv4route – 
                                         +днс (HQ-SRV) echo nameserver (192.168.100.2) > /etc/net/ifaces/ens192/resolv.conf
                                           Systemctl restart network ip a
