---
title: "/SAFESEH(이미지에 안전한 예외 처리기 포함) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/SAFESEH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SAFESEH 링커 옵션"
  - "-SAFESEH 링커 옵션"
  - "SAFESEH 링커 옵션"
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SAFESEH(이미지에 안전한 예외 처리기 포함)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SAFESEH[:NO]  
```  
  
 **\/SAFESEH**를 지정하면 링커에서는 이미지의 안전한 예외 처리기 테이블을 만들 수 있을 경우에만 이미지를 생성합니다.  이 테이블은 해당 운영 체제에서 해당 이미지에 올바른 예외 처리기를 지정합니다.  
  
 **\/SAFESEH**는 x86을 대상으로 링크할 때만 사용할 수 있습니다.  예외 처리기가 이미 포함되어 있는 플랫폼에 대해서는 **\/SAFESEH**가 지원되지 않습니다.  예를 들어 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 와 ARM 에서는 모든 예외 처리기가 PDATA에 포함되어 있습니다.  ML64.exe는 SEH 정보\(XDATA 및 PDATA\)를 이미지에 생성하는 주석을 추가하는 기능을 지원합니다. 이 기능을 통해 ml64 함수에서 해제할 수 있습니다.  자세한 내용은 [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)를 참조하십시오.  
  
 **\/SAFESEH**를 지정하지 않은 경우 링커에서는 모든 모듈이 안전한 예외 처리 기능과 호환될 때만 안전한 예외 처리기 테이블이 있는 이미지를 생성합니다.  안전한 예외 처리 기능과 호환되지 않는 모듈이 있으면 결과적으로 만들어지는 이미지에 안전한 예외 처리기 테이블이 포함되지 않습니다.  [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)에서 WINDOWSCE 또는 EFI\_\* 옵션 중 하나를 지정할 경우에는 링커에서 안전한 예외 처리기 테이블이 있는 이미지를 생성하려고 시도하지 않습니다. 이러한 하위 시스템에서는 해당 정보를 사용할 수 없기 때문입니다.  
  
 **\/SAFESEH:NO**를 지정하면 링커에서는 모든 모듈이 안전한 예외 처리 기능과 호환되더라도 안전한 예외 처리기 테이블이 있는 이미지를 생성하지 않습니다.  
  
 링커에서 이미지를 생성할 수 없는 가장 일반적인 이유는 링커에 대한 입력 파일\(모듈\) 중 하나 이상이 안전한 예외 처리기 기능과 호환되지 않기 때문입니다.  또한 모듈이 안전한 예외 처리기와 호환되지 않는 일반적인 이유는 모듈이 이전 버전의 Visual C\+\+ 컴파일러로 만들어졌기 때문입니다.  
  
 [.SAFESEH](../../assembler/masm/dot-safeseh.md)를 사용하여 함수를 구조적 예외 처리기로 등록할 수도 있습니다.  
  
 안전한 예외 처리기가 있거나 예외 처리기가 없는 것으로 기존 이진 데이터를 표시할 수 없습니다. 안전한 예외 처리에 대한 정보는 빌드할 때 추가되어야 합니다.  
  
 링커에서 안전한 예외 처리기 테이블을 만들 수 있는지 여부는 C 런타임 라이브러리를 사용하는 응용 프로그램에 따라 결정됩니다.  [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)를 사용하여 링크하면서 안전한 예외 처리기 테이블이 필요한 경우에는 loadcfg.c CRT 소스 파일과 같이 Visual C\+\+용으로 정의된 모든 항목이 들어 있는 로드 구성 구조를 제공해야 합니다.  예를 들면 다음과 같습니다.  
  
```  
#include <windows.h>  
extern DWORD_PTR __security_cookie;  /* /GS security cookie */  
  
/*  
 * The following two names are automatically created by the linker for any  
 * image that has the safe exception table present.  
*/  
  
extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */  
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is  
                                           the count of table entries */  
typedef struct {  
    DWORD       Size;  
    DWORD       TimeDateStamp;  
    WORD        MajorVersion;  
    WORD        MinorVersion;  
    DWORD       GlobalFlagsClear;  
    DWORD       GlobalFlagsSet;  
    DWORD       CriticalSectionDefaultTimeout;  
    DWORD       DeCommitFreeBlockThreshold;  
    DWORD       DeCommitTotalFreeThreshold;  
    DWORD       LockPrefixTable;            // VA  
    DWORD       MaximumAllocationSize;  
    DWORD       VirtualMemoryThreshold;  
    DWORD       ProcessHeapFlags;  
    DWORD       ProcessAffinityMask;  
    WORD        CSDVersion;  
    WORD        Reserved1;  
    DWORD       EditList;                   // VA  
    DWORD_PTR   *SecurityCookie;  
    PVOID       *SEHandlerTable;  
    DWORD       SEHandlerCount;  
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;  
  
const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {  
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    &__security_cookie,  
    __safe_se_handler_table,  
    (DWORD)(DWORD_PTR) &__safe_se_handler_count  
};  
```  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)