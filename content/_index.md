+++
title = "Terraform Workshop"
outputs = ["Reveal"]
+++

### About Terraform

* Infrastructure as Code
* Hashicorp Configuration Language (HCL)
* Keeps track of infrastructure state
* Supports multiple cloud providers
* Open Source

---
![Terraform Process](/terraform01.png)

---

### HCL Syntax

```hcl
resource "aws_s3_bucket" "s3_bucket" {
  bucket        = var.bucket_name   
  force_destroy = true
}

resource "aws_s3_bucket_acl" "s3_bucket" {
  bucket = aws_s3_bucket.s3_bucket.bucket
  acl    = "private"
}

resource "aws_s3_bucket_policy" "cloudfront" {  
  bucket = aws_s3_bucket.s3_bucket.id  
  policy = data.aws_iam_policy_document.cloudfront.json
}
```

---
### Terraform State


|                      |       |
| -------------------- | :---: |
| terraform.tfstate    |   🔴   |
| Terraform Cloud      |   🟢   |
| Hashicorp Consul     |   🟢   |
| AWS S3               |   🟡   |
| Azure Blob Storage   |   🟡   |
| Google Cloud Storage |   🟡   |


---

![Deployment](/terraform02.png)

---

# DEMO

---

### Github OIDC

![OIDC](/terraform03.png)

---

# Thank you!