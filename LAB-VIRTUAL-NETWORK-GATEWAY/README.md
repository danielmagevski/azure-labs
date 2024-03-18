# Criar uma conexão VPN site to site com Virtual Network Gateway

&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Arquitetura do LAB

![Arquitetura-2](https://github.com/danielmagevski/azure-labs/assets/10622331/ce4eaa52-2a9b-4f92-a78e-6e956766bbc3)

## Criar Resource Group
* RG-LAB-ONPREMISES
 
![RG-LAB-ONPREMISES](https://github.com/danielmagevski/azure-labs/assets/10622331/6235fa8c-7b60-47da-8407-8dd91dd7d777)

## Criar um Virtual Network Gateway (VNG)

* VNG-01

![VNG](https://github.com/danielmagevski/azure-labs/assets/10622331/524ad784-c672-49e7-8b5f-56c14ae01a12)

## Criar uma estrutura de rede para simular um ambiente On-Premises.

* VNET-ONPREMISES

![VNET-ONPREMISES](https://github.com/danielmagevski/azure-labs/assets/10622331/85399642-7439-464a-b0c1-11cfe4a192ca)

![VNET-ONPREMISES2](https://github.com/danielmagevski/azure-labs/assets/10622331/d4b5f2f8-fb36-45d8-87d6-9cd293796f4c)

## Criar uma VM Windows para simular um FW ON-PREMISES

* VM-FW-ONPREMISES

![VM-FW-ONPRIMISES](https://github.com/danielmagevski/azure-labs/assets/10622331/c1cdd9d6-5323-4f36-80e6-88025b488218)

![VM-ONPRIMISES2](https://github.com/danielmagevski/azure-labs/assets/10622331/fca78a76-2990-47c0-b17d-83d2b5da4576)

* Configurar RAS

<img width="526" alt="RAS1" src="https://github.com/danielmagevski/azure-labs/assets/10622331/31ea26fe-ef11-4dc7-8adf-d23d8f9d8bc1">

<img width="661" alt="RAS2" src="https://github.com/danielmagevski/azure-labs/assets/10622331/cf466446-3f9e-4b14-99e5-58cd36a6b027">

## Criar um Local Network Gateway

* VPN-ONPRIMISES

![LNG](https://github.com/danielmagevski/azure-labs/assets/10622331/763e321f-2cbc-4dc4-8f5b-381df1fcc295)

## Criar a conexão site to site

![CONN1](https://github.com/danielmagevski/azure-labs/assets/10622331/2771017c-e68f-4823-ae5b-6cf758e3ac09)

![CONN2](https://github.com/danielmagevski/azure-labs/assets/10622331/4648b0e8-5c86-41b4-b78d-a1525cbc3b03)

# Habilitar o virtual network gateway para que a VNET no Brazil utilize o Virtual Network Gateway passando por EAST US

* Peering USA01 to BRA01

![USA-to-BRA](https://github.com/danielmagevski/azure-labs/assets/10622331/d765cc6e-7912-4344-a23b-82aafd58766e)

* Peering BRA01 to USA01

![USA-to-BRA](https://github.com/danielmagevski/azure-labs/assets/10622331/6618374e-4145-4633-a0d4-a4d3eba02ea9)

* Peering USA01 to BRA01

 ![BRA-to-USA](https://github.com/danielmagevski/azure-labs/assets/10622331/44d36198-05b4-4f81-a5ed-f6bab54223fb)

 # Teste de conexão

 * VNET em BRA01

<img width="799" alt="PING1" src="https://github.com/danielmagevski/azure-labs/assets/10622331/2f2ed2af-cd97-4e56-b276-fd561c3a24d0">

* VNET em USA01

<img width="820" alt="PING2" src="https://github.com/danielmagevski/azure-labs/assets/10622331/cdb03d45-f314-4d9f-9224-e20ab62aea91">










