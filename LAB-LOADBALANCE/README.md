# Criar um Load Balancer e configurar e as configurar as VMs no Backend Pool

&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Arquitetura do LAB

![LAB-LOADBALANCER](https://github.com/danielmagevski/azure-labs/assets/10622331/a376c40f-cf74-4cac-8c94-bfb68ce562ed)

## Criar Resource Group
* RG-LAB
  
![RG-LAB](https://github.com/danielmagevski/azure-labs/assets/10622331/38aef132-4dde-4659-bea2-4b69214e20fc)

## Criar VNET
* VNET-WEB01
  
![VNET-WEB01](https://github.com/danielmagevski/azure-labs/assets/10622331/78df1df5-ae8c-4cc8-8d77-e7c42704cec9)

![VNET-SUBNETS](https://github.com/danielmagevski/azure-labs/assets/10622331/a6ee3972-1a46-4e88-bacd-d140afb944d3)

## Criar Network Security Group (NSG)
* NSG-WEB01

![NSG-WEB01](https://github.com/danielmagevski/azure-labs/assets/10622331/cc902fd1-e0a1-4b0e-9915-10769945feb0)

## Associar o NGS as subnets
* Associar as subnets da VNET criada

![NSG-SUBNETS](https://github.com/danielmagevski/azure-labs/assets/10622331/c401c117-28c5-4c58-bebf-9ef241cc1089)

## Crias as VMS

* VM-WEB01 na Zona 1

![VM-WEB01](https://github.com/danielmagevski/azure-labs/assets/10622331/392d5a0a-1cee-47c2-84d9-79ac135fec23)

![VM-WEB01-2](https://github.com/danielmagevski/azure-labs/assets/10622331/7752c2b8-e027-40f3-9e64-18997f7d3a82)

* VM-WEB02 na Zona 2

![VM-WEB02](https://github.com/danielmagevski/azure-labs/assets/10622331/3b6aae47-4b59-4678-b444-bcd62ebc17d7)

![VM-WEB02-2](https://github.com/danielmagevski/azure-labs/assets/10622331/ed740669-1018-4dcb-aec4-9d95a76d4059)

## Executar o Run command para instalar o IIS

* Como as VMs não tem IP público utilizei o Run command para instalar o IIS e customizar a página default

```
#Install IIS 
Install-WindowsFeature -name Web-Server -IncludeManagementTools 

#Remove default htm file 
remove-item C:\inetpub\wwwroot\iisstart.htm

#Add custom htm file 
Add-Content -Path "C:\inetpub\wwwroot\iisstart.htm" -Value $("LAB Load Balancer  -" + $env:computername)
```
![RUN-COMMAND](https://github.com/danielmagevski/azure-labs/assets/10622331/b8e57bba-6617-4766-9b91-d4f85458cc25)

## Criar e configurar um Load Balancer

* LB-WEB01

![LB-WEB01](https://github.com/danielmagevski/azure-labs/assets/10622331/d7f00125-ad6a-4dd9-8fdd-d018b97dcf93")

* Configurar o Frontend IP

![FRT-WEB-80](https://github.com/danielmagevski/azure-labs/assets/10622331/a89b997a-dd03-4774-a0bc-41a65d845ab1")

* Adicionar Backend Pool

![BKP-WEB]("https://github.com/danielmagevski/azure-labs/assets/10622331/6b6167c8-92db-4196-ad54-21982bafdb8f")

* Adicionar regra de entrada

![RULE-WEB01](https://github.com/danielmagevski/azure-labs/assets/10622331/891363a5-f0d6-4a0a-bc15-dd50b1775df4)

* Revisar e validar as configurações

![LB-WEB-REVIEW](https://github.com/danielmagevski/azure-labs/assets/10622331/ea03a382-2bfa-45cd-88a9-b9cdf0660ce6)

## Configurar o NSG para liberar o tráfego no Load Balancer

* Regra para liberar HTTP

![NSG-RULE](https://github.com/danielmagevski/azure-labs/assets/10622331/a5fe9987-83a2-469b-b7f9-0b2b5ff833ca)











