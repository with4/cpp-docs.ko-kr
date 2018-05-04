---
title: -SAFESEH (이미지에 안전한 예외 처리기를 포함) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54d13e6922650f0193d4bbc3469d4acf25904234
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH(이미지에 안전한 예외 처리기 포함)
```  
/SAFESEH[:NO]  
```  
  
 때 **/SAFESEH** 지정, 링커에서 이미지의 안전한 예외 처리기 테이블을 만들 수 있을 경우에 이미지를 생성 합니다. 이 테이블은 예외 처리기는 이미지에 사용할 운영 체제를 지정 합니다.  
  
 **/SAFESEH** x86에 대 한 연결 때만 유효 대상으로 합니다. **/SAFESEH** 예외 처리기에 이미 있는 플랫폼에 대 한 지원 되지 않습니다. 예를 들어 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 및 ARM에서는 모든 예외 처리기가 PDATA에 표시됩니다. ML64.exe는 ml64 함수를 통해 해제할 수 있도록 이미지에 추가 (XDATA 및 PDATA) SEH 정보를 생성 하는 주석을 지원 합니다. 참조 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md) 자세한 정보에 대 한 합니다.  
  
 경우 **/SAFESEH** 을 지정 하지 않으면 링커는 모든 모듈 안전한 예외 처리 기능과 호환 될 때만 안전한 예외 처리기 테이블을 사용 하 여 이미지를 생성 합니다. 모든 모듈 안전한 예외 처리 기능과 호환 되었으면 결과 이미지에 안전한 예외 처리기 테이블을 포함 되지 않습니다. 경우 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) WINDOWSCE 또는 EFI_ * 옵션 중 하나를 지정 수 모두 하위 시스템으로 안전한 예외 처리기 테이블을 사용 하 여 이미지를 생성 하기 위해 링커 시도 하지 것입니다는 정보를 사용 합니다.  
  
 경우 **/SAFESEH:NO** 를 지정 링커는 모든 모듈 안전한 예외 처리 기능과와 호환 되는 경우에 안전한 예외 처리기 테이블을 사용 하 여 이미지를 생성 하지 않습니다.  
  
 이미지를 생성할 수 링커에 대 한 가장 일반적인 이유 하나 이상의 입력된 파일 (모듈)을 링커에 안전한 예외 처리기 기능과 호환 되지 않았습니다. 때문입니다. 안전한 예외 처리기와 호환 되지 모듈에 대 한 일반적인 이유에는 이전 버전의 Visual c + + 컴파일러로 작성 되었으므로입니다.  
  
 사용 하 여 구조적된 예외 처리기로 함수를 등록할 수도 있습니다 [합니다. SAFESEH](../../assembler/masm/dot-safeseh.md)합니다.  
  
 기존 표시할 수 없는 이진 또는 있는 것으로 안전한 예외 처리기 (예외 처리기가 없는); 빌드 시에 안전한 예외 처리에 대 한 정보를 추가 합니다.  
  
 C 런타임 라이브러리를 사용 하 여 응용 프로그램에 안전한 예외 처리기 테이블을 작성 하는 링커의 기능에 따라 다릅니다. 사용 하 여 링크 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 안전한 예외 처리기 테이블, (예: loadcfg.c CRT 소스 파일에서 확인할 수 있습니다) 로드 구성 구조를 제공 해야 하 고 Visual c + +에 대해 정의 된 모든 항목을 포함 하 합니다. 예를 들어:  
  
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
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **링커** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  에 옵션을 입력에서 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)