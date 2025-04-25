data "oci_identity_tenancy" "tenancy" {
  tenancy_id = "ocid1.tenancy.oc1..aaaaaaaaamtvtn7a7y4b7mo7yihimhfbjf5wqhqyzist7djdnkoatxyqkq5aa"
}

output "tenancy_name" {
  value = data.oci_identity_tenancy.tenancy.name
}
