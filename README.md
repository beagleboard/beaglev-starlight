## BeagleV Starlight hardware design
* [BeagleV Starlight](https://beagleboard.org/beaglev) is the official name for the BeagleBoard.org RISC-V board with the StarFive 71x0 SoC
* Documentation:
  * [BeagleV Starlight Getting Started guide](https://wiki.seeedstudio.com/BeagleV-Getting-Started/)
  * [StarFive JH7100 SoC datasheet](https://github.com/starfive-tech/beaglev_doc/blob/main/JH7100%20Data%20Sheet%20V01.01.04-EN%20(4-21-2021).pdf)
  * [SiFive U7 core manual](https://github.com/starfive-tech/beaglev_doc/blob/main/vic_u7_manual_with_creativecommons.pdf)
* Tutorials:
  * [Getting Started with BeagleV™ - StarLight](https://wiki.seeedstudio.com/BeagleV-Getting-Started/)
  * [How to Make File System, Compile u-boot and Linux Kernel](https://wiki.seeedstudio.com/BeagleV-Make-File-System-Compile-uboot-Kernal/)
  * [Update bootloader, ddr init boot, u-boot and Recover bootloader](https://wiki.seeedstudio.com/BeagleV-Update-bootloader-ddr-init-boot-uboot-Recover-bootloader/)
* Code:
  * [Fedora image](https://github.com/starfive-tech/beaglev_fedora)
  * [Linux 5.10](https://github.com/starfive-tech/linux)
  * [U-Boot 2021.04](https://github.com/starfive-tech/u-boot)
  * [OpenSBI v0.9](https://github.com/starfive-tech/opensbi)
  * [StarFive Freelight U SDK](https://github.com/starfive-tech/freelight-u-sdk)
  * [secondBoot](https://github.com/starfive-tech/beagle_secondBoot)
  * [ddrinit](https://github.com/starfive-tech/beagle_ddrlnit)
* PCB design:
  * **Please open hardware issues in this repository**
  * `BeagleV v0.9.DSN`: Cadence OrCAD schematic
  * `BeagleV_15.brd`: Cadence Allegro board layout
    * Cadence Allegro Viewer can be [downloaded from Cadence](https://www.cadence.com/en_US/home/tools/pcb-design-and-analysis/allegro-downloads-start.html)
    * compressed in zip file to be under 100MB
  * `LIBRARY1.OLB`: Cadence OrCAD schematic library
  * `BEAGLE V.opj`: Cadence OrCAD project file
* Discussion forum:
  * [BeagleV public group](https://forum.beagleboard.org/c/beaglev-beta/16)
  * [BeagleV beta developer group](https://forum.beagleboard.org/c/beaglev-beta/16)
    * note: this is a private, contact Drew Fustini (drew at beagleboard.org)
* License:
  * [CERN-OHL-P (permissive)](https://ohwr.org/cern_ohl_p_v2.txt)
  * More information on [CERN Open Hardware License (OHL) v2](https://ohwr.org/project/cernohl/wikis/home)


### Guidance on naming conventions
* Spelling should be BeagleV not Beagle-V
  * BeagleV is BeagleBoard.org Foundation's name for RISC-V boards
* The board name is [BeagleV Starlight](https://github.com/beagleboard/beaglev-starlight) for this board.
  * The board that limited number of developers have thus far received is beta version of the BeagleV Starlight
  * [This FAQ](https://wiki.seeedstudio.com/BeagleV-Getting-Started/#faq) describes difference between beta and production.
* Board vendor is BeagleBoard.org Foundation
  * BeagleV Starlight is manufactured by Seeed Studio for BeagleBoard.org Foundation
  * Refer to`"^beagle,.*"` in [vendor-prefixes.yaml](https://www.kernel.org/doc/Documentation/devicetree/bindings/)
* StarFive SoC: VIC renamed to JH
  * The beta BeagleV Starlight board has StarFive JH7100 SoC
  * StarFive had referred it internally as VIC7100 but the public name is JH7100
  * StarFive has renamed datasheet to [JH7100](https://github.com/starfive-tech/beaglev_doc/blob/main/JH7100%20Data%20Sheet%20V01.01.04-EN%20(4-21-2021).pdf)
  * There are still many references to VIC and VIC7100 instead of JH7100 which will be cleaned up
* StarFive JH7100 versus JH7110
  * The beta BeagleV Starlight board has the StarFive JH7100
  * StarFive JH7110 is mass production chip which will be used in future BeagleV Starlight boards
    *  JH7110 upgrade from 2x to 4x U74 cores and adds PCIe and GPU
  * Recommendation is to use `beagle,beaglev-starlight-jh7100` and `beagle,beaglev-starlight-jh7110` to differientate between the board versions
* SiFive cores in the StarFive SoC:
  * StarFive JH7100 SoC has 2x SiFive U74-MC
  * StarFive JH7110 SoC will have 4x SiFive U74-MC
  * Datasheet: [U7 Core Manual](https://github.com/starfive-tech/beaglev_doc/blob/main/vic_u7_manual_with_creativecommons.pdf)
