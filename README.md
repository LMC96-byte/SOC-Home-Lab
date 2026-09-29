# 🛡️ SOC Home Lab

Laboratorio práctico de ciberseguridad y monitorización SOC construido con VirtualBox.

El objetivo de este proyecto es simular un entorno básico de un SOC (Security Operations Center), utilizando un equipo atacante, una máquina víctima y una plataforma de monitorización y detección.

## 🏗️ Arquitectura

El laboratorio está compuesto por tres máquinas virtuales:

| Máquina | Sistema | IP SOC-LAB | Función |
|---|---|---:|---|
| Kali | Kali Linux | `192.168.50.10` | Atacante |
| Windows | Windows 11 | `192.168.50.20` | Víctima |
| Security Onion | Security Onion | `192.168.50.1` | Monitorización / IDS |

La red interna del laboratorio utiliza:

```text
192.168.50.0/24

### Topología

```text
                    SOC-LAB
                 192.168.50.0/24
                       │
          ┌────────────┼────────────┐
          │            │            │
     Kali Linux     Windows 11   Security Onion
     192.168.50.10  192.168.50.20 192.168.50.1
       ATACANTE        VÍCTIMA          SOC
                                      │
                                      │
                                  👁️ Sniffing
