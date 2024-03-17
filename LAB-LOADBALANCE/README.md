# Criar um Load Balancer

&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Arquitetura do LAB


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

# Crias as VMS

* VM1

* VM2

# Executar o Run command para instalar o ISS

```
#Install IIS 
Install-WindowsFeature -name Web-Server -IncludeManagementTools 

#Remove default htm file 
remove-item C:\inetpub\wwwroot\iisstart.htm

#Add custom htm file 
Add-Content -Path "C:\inetpub\wwwroot\iisstart.htm" -Value $("LAB Load Balancer  -" + $env:computername)
```