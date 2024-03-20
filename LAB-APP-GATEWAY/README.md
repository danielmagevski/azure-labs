# Criar um Application Gateway com multiplos pools backend

&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Arquitetura do LAB

![LAB-APPGW](https://github.com/danielmagevski/azure-labs/assets/10622331/06680209-b053-4381-8b6b-f0af4e02415e)

## Criar Resource Group
* RG-LAB

![VNET-WEB01](https://github.com/danielmagevski/azure-labs/assets/10622331/55083b33-61e8-48ec-8a84-8f8e8491f6c9)

## Criar VNET com as Subnets
* VNET-APPGW

![VNET-APPGW](https://github.com/danielmagevski/azure-labs/assets/10622331/85f41fff-efa5-4c01-9472-68420892f4b2)
![VNET-SUBNETS](https://github.com/danielmagevski/azure-labs/assets/10622331/0fd05570-06a1-4e96-9f5a-96604a5cfe0d)

## Criar Network Security Group
* NSG01
![NSG](https://github.com/danielmagevski/azure-labs/assets/10622331/39d124f7-920b-4634-9559-cf80389ed268)

## Associar nas Subnets

![ASSOCIAR-SUBNETS](https://github.com/danielmagevski/azure-labs/assets/10622331/ad5e4166-0d1e-43cf-9423-6a88b3d69372)

## Criar VMs
* VM-WEB-01
  
![WM-WEB01](https://github.com/danielmagevski/azure-labs/assets/10622331/07094284-f820-4f79-97f6-2cf69bfef77c)
![VM-WEB01-2](https://github.com/danielmagevski/azure-labs/assets/10622331/14229441-5bf1-45fc-aadc-415d7f189b31)

* VM-WEB-02

![VM-WEB02](https://github.com/danielmagevski/azure-labs/assets/10622331/2024778e-1828-455c-8ed7-b34d1ee5a1b1)
![VM-WEB02-2](https://github.com/danielmagevski/azure-labs/assets/10622331/9f6cdb16-97c8-488f-833b-162bd7e20bc4)

## Instalar o ISS e criar os diretorios via Run Command
* VM-WEB01 e repetior o processo na VM-WEB02

![RUN-COMMAND](https://github.com/danielmagevski/azure-labs/assets/10622331/48152960-b220-46d7-97a9-7aba6715168c)

```
# Instalar IIS com Management Tools
Add-WindowsFeature Web-Server -IncludeManagementTools

# Remover a pagina iisstart 
remove-item C:\inetpub\wwwroot\iisstart.htm

# Configurar as paginas Default
Add-Content -Path "C:\inetpub\wwwroot\Default.htm" -Value "LAB APP-GATEWAY   $($env:computername)"

# Configurar a URL dos Paths
New-Item -ItemType directory -Path "C:\inetpub\wwwroot\images"
New-Item -ItemType directory -Path "C:\inetpub\wwwroot\video"

# Configurar Paginas baseadas no Path
$imagesvalue = "***URL-Path IMAGES*** - $($env:computername)"
Add-Content -Path "C:\inetpub\wwwroot\images\default.htm" -Value $imagesvalue
$videovalue = "***URL-Path VIDEO*** - $($env:computername)"
Add-Content -Path "C:\inetpub\wwwroot\video\default.htm" -Value $videovalue
```
## Liberar regra no NSG
* Regra de entrada para as maquinas criadas na porta HTTP

![NGS-RULE](https://github.com/danielmagevski/azure-labs/assets/10622331/2fde3d19-f4bd-443d-a6e5-0d810ae7db62)

## Criar o Application Load Balancer
* APPGW-WEB01
![APPGW](https://github.com/danielmagevski/azure-labs/assets/10622331/ebdf360d-f54f-4381-93b6-fe6cd5dc1d58)
![APPGW2](https://github.com/danielmagevski/azure-labs/assets/10622331/d377e78b-1914-4b10-84e1-9fb59c4e4c80)

* Adicionar Backend Pool
![APPGW3](https://github.com/danielmagevski/azure-labs/assets/10622331/2ceaa875-f56d-4844-9544-f56f844e2933)

* Adicionar regra de roteamento
![APPGW4](https://github.com/danielmagevski/azure-labs/assets/10622331/9715073d-3782-4a66-b91a-5830198f675c)
![APPGW5](https://github.com/danielmagevski/azure-labs/assets/10622331/b537ba88-8b62-4a87-a980-698d1e90f1ca)
![APPGW6](https://github.com/danielmagevski/azure-labs/assets/10622331/d64dc436-72ed-45a4-a71b-ade9e9c9c140)
![APPGW7](https://github.com/danielmagevski/azure-labs/assets/10622331/e31dc6d0-a91c-47f9-9eac-38f589acee9a)

* Resumo da criação do Application Load Balancer
![APPGW8](https://github.com/danielmagevski/azure-labs/assets/10622331/5f027f2c-f394-46e3-8b5d-ddc212d2ec52)

* Adicionar probe para monitorar a saude do backend pool
![APPGW9](https://github.com/danielmagevski/azure-labs/assets/10622331/0b70f35f-3388-4e0a-85d0-6821ebdf1238)

* Adicionar as regras para IMAGES e VIDEO
![APPGW10](https://github.com/danielmagevski/azure-labs/assets/10622331/920ac651-c3d5-4cb3-a562-5c1a91b38a0e)
