This is complete config to work with this module

## Usage
```
module "vpc" {
  source = "./module/vpc"

  vpc_config = {
    cidr_block = "10.0.0.0/16"
    name = "your_vpc_name"
  }

  subnet_config = {
    public_subnet = {
      cidr_block = "10.0.0.0/24"
      az = "ap-south-1a"
      #To set the subnet public, Default private
      public = true
    }
    private_subnet = {
      cidr_block = "10.0.1.0/24"
      az = "ap-south-1b"
    }
  }
}
```