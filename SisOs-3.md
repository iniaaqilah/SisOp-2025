# Proses Boot Sistem Operasi

Berikut adalah flowchart proses booting sistem operasi dari **Power On** hingga **OS Siap Digunakan**.

## Flowchart OS
```mermaid
flowchart TD
    A[POWER ON] --> B[BIOS/UEFI START-Load Bios / Uefi from Nvram]
    B --> C[POST: Power-On Self-Test]
    C --> D[Select Boot Device - Identify EFI system Partition]
    D --> E[Load Bootloader - Determine Witch Kernel to Boot]
    E --> F[Load Kernel OS - Instantiate Kernel Data Structures]
    F --> G[Probe for Hardware]
    G --> H[Initialisasi OS]
    H --> I[Execute Startup Scripts]
    I --> J[OS Siap Digunakan]
