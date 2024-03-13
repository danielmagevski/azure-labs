# Cria um rede Hub-Spoke com 3 VNETs e DNS Privado

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Arquitetura do LAB

![Arquitetura](https://github.com/danielmagevski/azure-labs/assets/10622331/182fc597-6e07-4949-bd62-4fda465cf388)

## Criar Resource Group
![RG-LAB](https://github.com/danielmagevski/azure-labs/assets/10622331/1a9e338b-5e74-4a19-ade2-7aa63f42b7a9)


## Criar Virtual Networks (VNET)

* VNET-USA01
  
![VNET-USA01](https://github.com/danielmagevski/azure-labs/assets/10622331/40bb7611-2628-411b-9053-04efdbfc4e86)

![VNET-USA01-2](https://github.com/danielmagevski/azure-labs/assets/10622331/2545fbd0-1669-4b24-a6e3-80d82096d882)

* VNET-EUR01

![VNET-EUR-1](https://github.com/danielmagevski/azure-labs/assets/10622331/2a60d23e-55a1-44c1-ab50-be6e8f874db0)

![VNET-EUR01-2](https://github.com/danielmagevski/azure-labs/assets/10622331/1dd811e8-0306-4595-9b1b-2cd6e305e353)

* VNET-BRA01

![VNET-BRA01](https://github.com/danielmagevski/azure-labs/assets/10622331/f555e78d-ce44-479b-a797-164f29383df3)

![VNET-BRA01-2](https://github.com/danielmagevski/azure-labs/assets/10622331/9e98623e-e5ed-4ad5-acdb-859a963736fb)

## Criar peering entre VNETs.

* Peering VNET-USA01 -> VNET-BRA01

![PEERING-USA-BRA](https://github.com/danielmagevski/azure-labs/assets/10622331/04746ff5-9651-482f-9c4d-37986819810a)

* Peering VNET-USA01 -> VNET-EUR01

![PEERING-USA-EUR](https://github.com/danielmagevski/azure-labs/assets/10622331/f62ace80-5264-4eb9-9ffe-3efb1d861892)

## Criar 2 VMs em cada região para validar o peering

* Criar VM-LNX01

![VM-LNX01](https://github.com/danielmagevski/azure-labs/assets/10622331/14fb7b62-70d3-4ce4-b521-250b6b8b72ac)

![VM-LNX02](https://github.com/danielmagevski/azure-labs/assets/10622331/9f0036c5-8fc7-44dd-ae64-0af27ab78479)

* Criar VM-WIN01

![VM-WIN01](https://github.com/danielmagevski/azure-labs/assets/10622331/e3e8114d-ef06-4304-8a05-aaa7d9c689cc)

![VM-WIN02](https://github.com/danielmagevski/azure-labs/assets/10622331/5b90bc74-c67e-43cb-861b-22b68a1c0599)

* Testar conexão

![teste-ping](https://github.com/danielmagevski/azure-labs/assets/10622331/f2c0f21e-1f37-4698-a778-1c333b941a13)


## Criar Zona Privada e link para as VNETs

* Criar zona privada danielbr.com

![create-private-dns](https://github.com/danielmagevski/azure-labs/assets/10622331/27c4ae34-f120-488e-944c-73950a586f69)

* Link USA01

![LINK-USA01](https://github.com/danielmagevski/azure-labs/assets/10622331/79b5ab32-327d-49a9-9d92-020163fe506d)

* Link EUR01

![LINK-EUR01](https://github.com/danielmagevski/azure-labs/assets/10622331/934e0e62-a531-4af0-8266-4d49cd5e211c)

* Link BRA01

![LINK-BRA01](https://github.com/danielmagevski/azure-labs/assets/10622331/31ff616e-5d64-40e9-a77c-e40a2aa924d1)

* Visualizar os Links

![LINKS-DNS](https://github.com/danielmagevski/azure-labs/assets/10622331/fc4ce250-6f7e-428c-ab81-90aafd9830ae)


* Registro das VMs no DNS

![private-dns](https://github.com/danielmagevski/azure-labs/assets/10622331/a6b6dd3e-aacf-42b9-850b-64916f953826)



