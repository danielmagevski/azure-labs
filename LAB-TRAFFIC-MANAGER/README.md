# Criar um Traffic Manager e adicionar os profiles

&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Arquitetura do LAB

![traffic-manager](https://github.com/danielmagevski/azure-labs/assets/10622331/86d91ce4-3268-469e-b63b-21993d777421)


## Criar Resource Group
* RG-LAB

![RG-LAB](https://github.com/danielmagevski/azure-labs/assets/10622331/23c9627d-b2b2-4aff-8a4b-ba08d22b5115)

## Criar APP Service Plan

* appplan-eastus01

![PLAN-US](https://github.com/danielmagevski/azure-labs/assets/10622331/b8e4e3d9-b708-4d19-abdd-a7b31c5d813f)

* appplan-brazil01

![PLAN-BRAZIL](https://github.com/danielmagevski/azure-labs/assets/10622331/dc4be8d1-3a74-4e49-8ec2-aa1f47e67c41)

## Criar Web App

* appdanielmagevskibrazil

![WEBAPP-BRAZIL](https://github.com/danielmagevski/azure-labs/assets/10622331/6afafc39-fa88-4056-8d0d-2c96890b9e4c)

## Criar o Traffic Manager Profile

* danielmagevski

![TRAFFIC-PROFILE](https://github.com/danielmagevski/azure-labs/assets/10622331/a1009932-dcc8-421a-b618-d6eb3b5dd586)

## Adicionar Endpoint

* WEBAPP-EASTUS

![ENDPOINT-US](https://github.com/danielmagevski/azure-labs/assets/10622331/1f7b1a79-5307-4ed5-a165-b97caaaa891b)

* WEBAPP-BRAZIL

![ENDPOINT-BRAZIL](https://github.com/danielmagevski/azure-labs/assets/10622331/afdf8db9-b621-4f6f-b94f-1a77ee232f65)

## Validar os profiles

* Profile BRAZIL
* Como estou no Brasil e está configurado perfomance esse é o padrão, para testar o outro precisei parar o WEB APP nessa região

![PROFILE-BRAZIL](https://github.com/danielmagevski/azure-labs/assets/10622331/b282ce76-6bf4-4e9d-b0ba-8f0237b9d3b3)

* Profile EAST US

![PROFILE-US](https://github.com/danielmagevski/azure-labs/assets/10622331/f224a0d2-3448-4eeb-a6e6-dfdb800594b3)

