---
Title | PECOFF
-- | --
Create Date | `2022-01-06T03:18:02Z`
Update Date | `2022-01-06T03:47:51Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/248)

---
## Reference
- [Microsoft Portable Executable and Common Object File Format Specification - Revision 8.3 (6th Feb, 2013).pdf](https://github.com/tpn/pdfs/blob/master/Microsoft%20Portable%20Executable%20and%20Common%20Object%20File%20Format%20Specification%20-%20Revision%208.3%20(6th%20Feb%2C%202013).pdf)  [[docx]](https://raw.githubusercontent.com/tpn/pdfs/master/Microsoft%20Portable%20Executable%20and%20Common%20Object%20File%20Format%20Specification%20-%20Revision%208.3%20(6th%20Feb%2C%202013).docx)

## Brief
- PE executable
- COFF Object-Module

## PE Executable

![image](https://user-images.githubusercontent.com/2216970/148322865-9ed5b594-e33f-4095-b339-696ebd477653.png)


## COFF

![image](https://user-images.githubusercontent.com/2216970/148322882-02ed8a6b-d4c4-48a1-bb9e-1bae0c26f5b6.png)

### File Headers
- COFF File Header(Object and Image)
- Optional Header(Image Only)

### Section Table


Section Name | Content
-- | --
.bss | Uninitialized data (free format)
.cormeta | CLR metadata that indicates that the object file contains managed code
.data | Initialized data (free format)
.debug$F | Generated FPO debug information (object only, x86 architecture only, and now obsolete)
.debug$P | Precompiled debug types (object only)
.debug$S | Debug symbols (object only)
.debug$T | Debug types (object only)
.drective | Linker options
.edata | Export tables
.idata | Import tables
.idlsym | Includes registered SEH (image only) to support IDL attributes. For information, see “IDL Attributes” in “References” at the end of this specification.
.pdata | Exception information
.rdata | Read-only initialized data
.reloc | Image relocations
.rsrc | Resource directory
.sbss | GP-relative uninitialized data (free format)
.sdata | GP-relative initialized data (free format)
.srdata | GP-relative read-only data (free format)
.sxdata | Registered exception handler data (free format and x86/object only)
.text | Executable code (free format)
.tls | Thread-local storage (object only)
.tls$ | Thread-local storage (object only)
.vsdata | GP-relative initialized data (free format and for ARM, SH4, and Thumb architectures only)
.xdata | Exception information (free format)



