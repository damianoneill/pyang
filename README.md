# pyang

Provide a container based solution (with all the required dependencies) for running [pyang](https://github.com/mbj4668/pyang).  

YANG (RFC 7950) is a data modeling language for NETCONF (RFC 6241), developed by the IETF NETMOD WG.

pyang is a YANG validator, transformator and code generator, written in python. It can be used to validate YANG modules for correctness, to transform YANG modules into other formats, and to generate code from the modules.

## Build the image

```sh
docker build -t damianoneill/pyang .
```

## Run the Image

```sh
docker run -it --rm damianoneill/pyang
```

## Use the Image

```sh
git clone https://github.com/OpenROADM/OpenROADM_MSA_Public.git 
```

```sh
pyang -f tree OpenROADM_MSA_Public/model/Device/org-openroadm-device.yang -p OpenROADM_MSA_Public/model/Common:OpenROADM_MSA_Public/model/Network:OpenROADM_MSA_Public/model/Service

module: org-openroadm-device
  +--rw org-openroadm-device
     +--rw info
     |  +--rw node-id?                            org-openroadm-common-node-types:node-id-type
     |  +--rw node-number?                        uint32
     |  +--rw node-type                           org-openroadm-device-types:node-types
     |  +--rw clli?                               string
     |  +--rw ipAddress?                          ietf-inet-types:ip-address
     |  +--rw prefix-length?                      uint8
     |  +--rw defaultGateway?                     ietf-inet-types:ip-address
     |  +--ro source?                             enumeration
     |  +--ro current-ipAddress?                  ietf-inet-types:ip-address
     |  +--ro current-prefix-length?              uint8
     |  +--ro current-defaultGateway?             ietf-inet-types:ip-address
     |  +--ro macAddress?                         ietf-yang-types:mac-address
     |  +-

     ...
```