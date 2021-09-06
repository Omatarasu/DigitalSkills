# Essential commands
Выбор default subscription ( чтобы каждый раз не вводить )
> az account set --subscription MySubscription

Создание Resource Group
> az group create --name MyGroup --location centralus

Удаление Resource Group
> az group delete --name MyGroup

Создание VNet
> az network vnet create --name MyVNet --resource-group MyGroup --address-prefixes 10.0.0.0/16 --subnet-name MySubNet --subnet-prefixes 10.0.0.0/24

удаление VNet
> az network vnet delete --name MyVNet --resource-group MyGroup
