# 🛡️ SOC Home Lab

Laboratorio práctico de ciberseguridad y monitorización SOC construido con VirtualBox.

El objetivo de este proyecto es simular un entorno básico de un SOC (Security Operations Center), utilizando un equipo atacante, una máquina víctima y una plataforma de monitorización y detección.

## 🏗️ Arquitectura

El laboratorio está compuesto por tres máquinas virtuales:

| Máquina | Sistema | IP SOC-LAB | Función |
|---|---|---|---|
| Kali | Kali Linux | `192.168.50.10` | Atacante |
| Windows | Windows 11 | `192.168.50.20` | Víctima |
| Security Onion | Security Onion | `192.168.50.1` | Monitorización / IDS |

La red interna del laboratorio utiliza:

`192.168.50.0/24`

### Topología

```text
                    SOC-LAB
                 192.168.50.0/24
                       |
          +------------+------------+
          |            |            |
     Kali Linux     Windows 11   Security Onion
     192.168.50.10  192.168.50.20 192.168.50.1
       ATACANTE        VÍCTIMA          SOC
                                      |
                                      |
                                  Sniffing
```

## 👁️ Monitorización de red

Security Onion cuenta con una interfaz dedicada de sniffing conectada a la red `SOC-LAB` y configurada en modo promiscuo.

Esta configuración permite a Security Onion observar y analizar el tráfico generado dentro del laboratorio sin que el tráfico tenga que atravesar físicamente el sistema de monitorización.

## 🎯 Objetivos del proyecto

- Generar actividad ofensiva controlada desde Kali Linux.
- Detectar dicha actividad mediante Security Onion.
- Analizar las alertas y evidencias obtenidas.
- Investigar los eventos desde la perspectiva de un analista SOC.
- Relacionar las técnicas observadas con MITRE ATT&CK.
- Documentar el proceso de investigación.
- Elaborar un informe de incidente.

## 🚧 Estado del proyecto

**Fase actual:** Laboratorio configurado y preparado para comenzar los escenarios de ataque y detección.

## 🧰 Tecnologías y herramientas

- VirtualBox
- Kali Linux
- Windows 11
- Security Onion
- Nmap
- Suricata
- Zeek
- tcpdump
