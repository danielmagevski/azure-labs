# Deploy da estrutura de VNETs e conexões peering

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Arquitetura do LAB

![arquitetura](https://github.com/danielmagevski/azure-labs/assets/10622331/c6be1faa-7cf6-4daa-b87c-042db14a7efb)


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

