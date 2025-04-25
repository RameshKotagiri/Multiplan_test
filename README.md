terraform {
  required_version = ">= 1.6.3"
  required_providers {
    oci = {
      source  = "oracle/oci"
      version = "6.23.0"
    }
  }
}

provider "oci" {
  config_file_profile = "DEFAULT"            # or "MyProfile"
  config_file_path    = "C:/Users/Ramesh/.oci/config"
}
