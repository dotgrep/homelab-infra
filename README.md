### 🌐 Physical Hardware Topology

```mermaid
flowchart TD
    %% Edge & Network Infrastructure
    WAN[🌐 WAN / Fiber Internet] --> EdgeRouter[MikroTik RouterOS Edge Router]
    EdgeRouter --> CoreSwitch[Managed Switch & 24-Port Patch Panel]

    %% Rack Core Hardware
    subgraph Network_Rack [ Homelab Rack Infrastructure ]
        CoreSwitch --> PVEHost1[Proxmox VE Host / Compute Node 1]
        CoreSwitch --> PVEHost2[Proxmox VE Host / Compute Node 2]
        CoreSwitch --> NASNode[Storage Server / ZimaOS NAS]
    end

    %% Access Layer
    CoreSwitch --> AP[Wireless Access Points]
