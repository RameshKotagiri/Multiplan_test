terraform {
  required_version = ">= 1.6.3"
  required_providers {
    oci = {
      source  = "oracle/oci"
      version = "6.23.0" # Update to the latest version
    }
  }
}
 
provider "oci" {
  config_file_profile = ".OCI"
}
