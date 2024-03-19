![NGS-RULE](https://github.com/danielmagevski/azure-labs/assets/10622331/c20d8f55-2143-4ccb-ae5a-443e25b36a37)


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
