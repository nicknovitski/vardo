# Vardo

The mission of this project is immortal and affordable personal computing for
developers.

Currently in the "laughably humble beginnings" stage, it consists of an [AWS
Cloudformation](https://aws.amazon.com/cloudformation/) template.

## Parameters

To instantiate the template, you must specify:
- An AMI (might I recommend [NixOS](https://nixos.org/nixos/download.html#amazon-ec2)?)
- An existing EC2 keypair for root ssh access

Optionally, you can also specify:
- A root volume size in gigabytes (defaults to 10, can be 5-50)
- An instance type (defaults to t2.medium, can be t2.small instead)
- An IP CIDR range from which to allow ssh access attempts (defaults to 0.0.0.0/0)

## Outputs

The template has one output: an elastic IP attached to the described instance.
You can ssh to it, and serve anything you like on unprivileged ports.

## Costs

AWS only charges you for instances while they're running, and most of the time,
you only need to run your workstation while you're using it.

Currently, EBS volumes cost 10¢ per gigabyte per month, Elastic IPs cost half a
cent per hour they _aren't_ in use, and t2.medium instances cost between 5-8¢
an hour.  Assuming 6¢, and 50 hours of usage a week, with a 30gb root volume,
that's about $18.30 a month.

## Related Work

I recommend installing [something that shuts the machine off automatically
after you disconnect](https://www.github.com/nicknovitski/occupado), to save your
money and attention, and also using [mosh](https://mosh.org) as an ssh client.

## Contributing

Contributions are extremely welcome, whether they take the form of code, ideas,
requests, issues, criticisms of fundamental assumptions, or even just usage.

Contact me for any reason at: vardo at-sign nicknovitski period com
