# Nutanix Terraform Cartographer

A single-file, browser-only design tool for the
[Nutanix Terraform provider](https://registry.terraform.io/providers/nutanix/nutanix/latest/docs).
Drag resources and data sources from a categorized palette onto a canvas, fill in their arguments
and inline configuration blocks (NICs, disks, sysprep / cloud-init, boot config, ip configs, …),
and export valid Terraform.

## Run it

`index.html` is the whole app. Open it in any modern browser:

```sh
# any of these work
open index.html
xdg-open index.html
start index.html
```

No server, no build step, no dependencies — everything is inlined.

## What's in the catalog

Every resource and data source from the live `nutanix/terraform-provider-nutanix` provider is
exposed (~120 resources, ~165 data sources). Popular types have rich, schema-driven editors
(VM, subnet, VPC, image, volume group, floating IP, network security policy, protection policy,
NDB family, Karbon, etc.). Less common types fall back to a name field plus a free-form HCL body.

The PC version dropdown in the top bar drives the `required_providers` constraint emitted in your
generated Terraform — the matrix follows the official compatibility table from the provider's
README.

## Usage notes

- Drag-box select multiple cards on the canvas; shift-click extends the selection.
- The right pane shows a node's full form — fields, inline configuration, and per-block
  add buttons. With multiple cards selected, the pane stacks all of them and offers batch
  Duplicate / Delete.
- Default values that match the schema are stripped from generated TF so the output only
  contains attributes the user actually changed.
- Clicking the **Provider Settings** label or the PC version dropdown surfaces the full
  provider config form in the right pane.

## License

[GPL-3.0](LICENSE).

## Security

See [SECURITY.md](SECURITY.md). Please use GitHub's private vulnerability reporting for any
security issues.
