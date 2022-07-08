    os_type           = "Windows"
  }

  os_profile {
    computer_name  = "windowsvM"
    admin_username = "itadmin"
    admin_password = "Password1234!"
  }
  os_profile_windows_config {}
}
    location   =   "East US"                                                                                                                                                                                 64,1          Bot
    resource_group_name   =   azurerm_resource_group.rg.name
  }

  resource   "azurerm_subnet"   "nonprodVPSXsubnet"   {
    name   =   "nonprod-VPSX-subnet" 
    resource_group_name   =    azurerm_resource_group.rg.name 
    virtual_network_name   =   azurerm_virtual_network.myvnet.name
    address_prefix   =   "10.0.1.0/24"
  }

  resource   "azurerm_network_interface"   "nonprod-VPSX-nic"   {
    name   =   "nonprod-VPSX-nic"
    location   =   "East US"
    resource_group_name   =   azurerm_resource_group.rg.name

    ip_configuration   {
      name   =   "nonprod-VPSX-ipconfig"
      subnet_id   =   azurerm_subnet.nonprodVPSXsubnet.id
      private_ip_address_allocation   =   "Dynamic"
   }
 }
 resource "azurerm_virtual_machine" "windows" {
   name                  = "aotsreprtn"
   resource_group_name   = azurerm_resource_group.rg.name
  location              = azurerm_resource_group.rg.location
  vm_size               = "Standard_B1ls"
    os_type           = "Windows"
  }
                          {
  os_profile {
    computer_name  = "windowsvM"
    admin_username = "itadmin"
    admin_password = "Password1234!"
  }
  os_profile_windows_config {}
}                 {
    name              = "changeme-os-disk-name"
    caching           = "ReadWrite"
    create_option     = "FromImage"
    managed_disk_type = "Standard_LRS"
    os_type           = "Windows"
  }

  os_profile {
    computer_name  = "windowsvM"
    admin_username = "itadmin"
    admin_password = "Password1234!"
  }
  os_profile_windows_config {}
}
    location   =   "East US"   