


## Criar Resource Group

## Criar VNET com as Subnets

## Criar NSG

## Associar nas Subnets

## Criar VMS

## Instalar o ISS e criar os diretorios via Run Command

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

## Criar o Application Load Balancer

#