# FSx for Lustre file systems should be configured to copy tags to backups

| Provider            | -Category |
| ------------------- | --------- |
| Amazon Web Services |  Tagging  |

## Description

This control checks whether an Amazon FSx for Lustre file system is configured to copy tags to backups and volumes. The control fails if the Lustre file system isn't configured to copy tags to backups and volumes.

Identification and inventory of your IT assets is an important aspect of governance and security. Tags help you categorize your AWS resources in different ways, for example, by purpose, owner, or environment. This is useful when you have many resources of the same type because you can quickly identify a specific resource based on the tags that you assigned to it.

This rule is covered by the [fsx-lustre-copy-tags-to-backups](https://github.com/hashicorp/policy-library-FSBP-Policy-Set-for-AWS-Terraform/blob/main/policies/fsx/fsx-lustre-copy-tags-to-backups.sentinel)

## Policy Results (Pass)

```bash
trace:
    Pass - fsx-lustre-copy-tags-to-backups.sentinel

    Description:
    This policy requires resources of type `aws_fsx_lustre_file_system` have the
    `copy_tags_to_backups` attributes set to true.

    Print messages:

    → → Overall Result: true

    This result means that all resources have passed the policy check for the policy fsx-lustre-copy-tags-to-backups-enabled.

    ✓ Found 0 resource violations

    fsx-lustre-copy-tags-to-backups.sentinel:48:1 - Rule "main"
    Value:
        true
```

---

## Policy Results (Fail)

```bash
trace:
    Fail - fsx-lustre-copy-tags-to-backups.sentinel

    Description:
    This policy requires resources of type `aws_fsx_lustre_file_system` have the
    `copy_tags_to_backups` attributes set to true.

    Print messages:

    → → Overall Result: false

    This result means that not all resources passed the policy check and the protected behavior is not allowed for the policy fsx-lustre-copy-tags-to-backups-enabled.

    Found 1 resource violations

    → Module name: root
    ↳ Resource Address: aws_fsx_lustre_file_system.example
        | ✗ failed
        | Attributes 'copy_tags_to_backups' must be true for 'aws_fsx_lustre_file_system' resources. Refer to https://docs.aws.amazon.com/securityhub/latest/userguide/fsx-controls.html#fsx-2 for more details.


    fsx-lustre-copy-tags-to-backups.sentinel:48:1 - Rule "main"
    Value:
        false
```

---
