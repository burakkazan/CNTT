[<< Back](../../ref_model)
# 5	Reference NFVI SW profiles and configurations
<p align="right"><img src="../figures/bogo_sdc.png" alt="scope" title="Scope" width="35%"/></p>

## Table of Contents
* [5.1 Basic NFVI reference SW profile and configuration.](#5.1)
  * [5.1.1 Virtual Compute.](#5.1.1)
  * [5.1.2 Virtual Storage.](#5.1.2)
  * [5.1.3 Virtual Networking and SDN.](#5.1.3)
  * [5.1.4 Security.](#5.1.4)
* [5.2 Network intensive NFVI reference SW profile and configuration.](#5.2)
  * [5.2.1 Virtual Compute.](#5.2.1)
  * [5.2.2 Virtual Storage.](#5.2.2)
  * [5.2.3 Virtual Networking and SDN.](#5.2.3)
  * [5.2.4 Security.](#5.2.4)
* [5.3 Compute intensive NFVI reference SW profile and configuration.](#5.3)
  * [5.3.1 Virtual Compute.](#5.3.1)
  * [5.3.2 Virtual Storage.](#5.3.2)
  * [5.3.3 Virtual Networking and SDN.](#5.3.3)
  * [5.3.4 Security.](#5.3.4)

Depending on the requirements of VNFs and the capabilities expected from the infrastructure, this area is defining the right infrastructure configuration that is needed for each profile.

<p align="center"><img src="../figures/ch05_ref_nfvi_sw_profiles.PNG" alt="ref_profiles" title="Reference Profiles" width="100%"/></p>
<p align="center"><b>Figure 5-1:</b> Reference NFVI software profiles.</p>

<a name="5.1"></a>
## 5.1	Basic NFVI reference SW profile and configuration
This NFVI SW Profile and configuration will be suitable for B instance type (Please see Section 3). **Figure 5-2** below shows the reference architecture of the NFVI solution.

<p align="center"><img src="../figures/ch05_b_ref_profile.PNG" alt="b_ref_profile" title="Basic Reference Profile" width="100%"/></p>
<p align="center"><b>Figure 5-2:</b> Reference NFVI software profile and configuration for B instance.</p>

<a name="5.1.1"></a>
### 5.1.1	Virtual Compute

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|----------------|----------------------------------|------------|------------------------------------------------------------------------------------------------|
| nfvi.com.cfg.001 | VM Flavours | All flavours listed in **Chapter 4** | Yes | Supported VM Flavours needs to be the same as those listed in the compute flavours' catalogue. |
| nfvi.com.cfg.002 | Hyperthreading | Enabled | Yes | Hyperthreading needs to be enabled and allowed. |
| nfvi.com.cfg.003 |  |  |  |  |

<p align="center"><b>Table 5-1:</b> Virtual Compute Configuration for B instance.</p>

#### 5.1.1.1	Virtual compute Acceleration

<a name="5.1.2"></a>
### 5.1.2	Virtual Storage

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|---------------|-----------------------------------|------------|--------------------------------------------------------------------------------|
| nfvi.stg.cfg.001 | Storage Types | All types listed in **Chapter 4** | Yes | Supported Storage types needs to be the same as those listed in the catalogue. |
| nfvi.stg.cfg.002 |  |  |  |  |
| nfvi.stg.cfg.003 |  |  |  |  |

<p align="center"><b>Table 5-2:</b> Virtual Storage Configuration for B instance.</p>

#### 5.1.2.1 Virtual storage Acceleration

<a name="5.1.3"></a>
### 5.1.3 Virtual Networking and SDN

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|---------------------------|--------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| nfvi.net.cfg.001 | vNIC interface | Virtio1.1 |  | vNIC interface needs to be virtio1.1. |
| nfvi.net.cfg.002 | Overlay protocol | VXLAN, MPLSoUDP, GENEVE, other |  | The overlay network encapsulation protocol needs to enable ECMP in the underlay to take advantage of the scale-out features of the network fabric. |
| nfvi.net.cfg.003 | SFC support |  |  |  |
| nfvi.net.cfg.004 | Traffic patterns symmetry |  |  | Traffic patterns should be optimal, in terms of packet flow. North-south traffic shall not be concentrated in specific elements in the architecture, making those critical choke-points, unless strictly necessary (i.e. when NAT 1:many is required). |
| nfvi.net.cfg.005 | Horizontal scaling |  |  | The VNF cluster must be able to scale horizontally and to leverage technologies such as ECMP to enable scale-outs/scale-ins, privileging Active-Active HA models, even though this may require some level of application re-design to cope with the need of sharing state between VNF instances |

<p align="center"><b>Table 5-3:</b> Virtual Networking & SDN Configuration for B instance.</p>

#### 5.1.3.1	Virtual Network Acceleration

<a name="5.1.4"></a>
### 5.1.4	Security

<a name="5.2"></a>
## 5.2	Network intensive NFVI reference SW profile and configuration
This NFVI SW Profile and configuration will be suitable for both B and N instance types.

<p align="center"><img src="../figures/ch05_n_ref_profile.PNG" alt="n_ref_profile" title="Network Intensive Reference Profile" width="100%"/></p>
<p align="center"><b>Figure 5-3:</b> Reference NFVI software profile and configuration for N instance.</p>

<a name="5.2.1"></a>
### 5.2.1	Virtual Compute

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|----------------|----------------------------------|------------|------------------------------------------------------------------------------------------------|
| nfvi.com.cfg.001 | VM Flavours | All flavours listed in **Chapter 4** | Yes | Supported VM Flavours needs to be the same as those listed in the compute flavours' catalogue. |
| nfvi.com.cfg.002 | Hyperthreading | Enabled | Yes | Hyperthreading needs to be enabled and allowed. |
| nfvi.com.cfg.003 |  |  |  |  |

<p align="center"><b>Table 5-4:</b> Virtual Compute Configuration for N instance.</p>


#### 5.2.1.1	Virtual compute Acceleration

<a name="5.2.2"></a>
### 5.2.2	Virtual Storage

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|---------------|-----------------------------------|------------|--------------------------------------------------------------------------------|
| nfvi.stg.cfg.001 | Storage Types | All types listed in **Chapter 4** | Yes | Supported Storage types needs to be the same as those listed in the catalogue. |
| nfvi.stg.cfg.002 |  |  |  |  |
| nfvi.stg.cfg.003 |  |  |  |  |

<p align="center"><b>Table 5-5:</b> Virtual Storage Configuration for N instance.</p>

#### 5.2.2.1	Virtual storage Acceleration

<a name="5.2.3"></a>
### 5.2.3	Virtual Networking and SDN

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|---------------------------|--------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| nfvi.net.cfg.001 | vNIC interface | Virtio1.1 |  | vNIC interface needs to be virtio1.1. |
| nfvi.net.cfg.002 | Overlay protocol | VXLAN, MPLSoUDP, GENEVE, other |  | The overlay network encapsulation protocol needs to enable ECMP in the underlay to take advantage of the scale-out features of the network fabric. |
| nfvi.net.cfg.003 | SFC support |  |  |  |
| nfvi.net.cfg.004 | Traffic patterns symmetry |  |  | Traffic patterns should be optimal, in terms of packet flow. North-south traffic shall not be concentrated in specific elements in the architecture, making those critical choke-points, unless strictly necessary (i.e. when NAT 1:many is required). |
| nfvi.net.cfg.005 | Horizontal scaling |  |  | The VNF cluster must be able to scale horizontally and to leverage technologies such as ECMP to enable scale-outs/scale-ins, privileging Active-Active HA models, even though this may require some level of application re-design to cope with the need of sharing state between VNF instances |
| nfvi.net.cfg.006 | vRouter/vSwitch |  |  | The vRouter/vSwitch elements must be optimised/accelerated and/or HW offloadable. |

<p align="center"><b>Table 5-6:</b> Virtual Networking & SDN Configuration for N instance.</p>

#### 5.2.3.1	Virtual Network Acceleration

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|-------------------------------|-------------------|------------|--------------------------------------------------|
| nfvi.acc.cfg.001 | Crypto Acceleration | Supported | No |  |
| nfvi.acc.cfg.002 | Crypto Acceleration Interface | VDPA/virtio-ipsec | Yes | To be decided what interface it needs to support |

<p align="center"><b>Table 5-7:</b> Virtual Acceleration configuration for N instance.</p>

<a name="5.2.4"></a>
### 5.2.4	Security

<a name="5.3"></a>
## 5.3	Compute intensive NFVI reference SW profile and configuration
This NFVI SW profile and configuration will be suitable for C instance type

<p align="center"><img src="../figures/ch05_c_ref_profile.PNG" alt="c_ref_profile" title="Compute Intensive Reference Profile" width="100%"/></p>
<p align="center"><b>Figure 5-4:</b> Reference NFVI software profile and configuration for C instance.</p>

<a name="5.3.1"></a>
### 5.3.1	Virtual Compute

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|----------------|----------------------------------|------------|------------------------------------------------------------------------------------------------|
| nfvi.com.cfg.001 | VM Flavours | All flavours listed in **Chapter 4** | Yes | Supported VM Flavours needs to be the same as those listed in the compute flavours' catalogue. |
| nfvi.com.cfg.002 | Hyperthreading | Enabled | Yes | Hyperthreading needs to be enabled and allowed. |
| nfvi.com.cfg.003 |  |  |  |  |

<p align="center"><b>Table 5-8:</b> Virtual Compute Configuration for C instance.</p>


#### 5.3.1.1	Virtual compute Acceleration

<a name="5.3.2"></a>
### 5.3.2	Virtual Storage

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|---------------|-----------------------------------|------------|--------------------------------------------------------------------------------|
| nfvi.stg.cfg.001 | Storage Types | All types listed in **Chapter 4** | Yes | Supported Storage types needs to be the same as those listed in the catalogue. |
| nfvi.stg.cfg.002 |  |  |  |  |
| nfvi.stg.cfg.003 |  |  |  |  |

<p align="center"><b>Table 5-9:</b> Virtual Storage Configuration for C instance.</p>

#### 5.3.2.1	Virtual storage Acceleration

<a name="5.3.3"></a>
### 5.3.3	Virtual Networking and SDN

| .conf | Feature | Configuration | Mandatory? | Description |
|------------------|---------------------------|--------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| nfvi.net.cfg.001 | vNIC interface | Virtio1.1 |  | vNIC interface needs to be virtio1.1. |
| nfvi.net.cfg.002 | Overlay protocol | VXLAN, MPLSoUDP, GENEVE, other |  | The overlay network encapsulation protocol needs to enable ECMP in the underlay to take advantage of the scale-out features of the network fabric. |
| nfvi.net.cfg.003 | SFC support |  |  |  |
| nfvi.net.cfg.004 | Traffic patterns symmetry |  |  | Traffic patterns should be optimal, in terms of packet flow. North-south traffic shall not be concentrated in specific elements in the architecture, making those critical choke-points, unless strictly necessary (i.e. when NAT 1:many is required). |
| nfvi.net.cfg.005 | Horizontal scaling |  |  | The VNF cluster must be able to scale horizontally and to leverage technologies such as ECMP to enable scale-outs/scale-ins, privileging Active-Active HA models, even though this may require some level of application re-design to cope with the need of sharing state between VNF instances |
| nfvi.net.cfg.006 | vRouter/vSwitch |  |  | The vRouter/vSwitch elements must be optimised/accelerated and/or HW offloadable. |

<p align="center"><b>Table 5-10:</b> Virtual Networking & SDN Configuration for C instance.</p>

#### 5.3.3.1	Virtual Network Acceleration

<a name="5.3.4"></a>
### 5.3.4	Security
