# terraform-aws-vpc

## Overview

This terraform module crestes an AWS VPC with a given CIDR block.
It also creates multiple subnets(private and public), and for public subnets, it sets up an Internet Gateway(IGW) and appropriate route table.

## Feature

- Creates a VPC with a specified CIDR block
- Creates public and private subnets
- Creates an Internet Gateway (IGW) for public subnets
- Sets up route tables for public subnets

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