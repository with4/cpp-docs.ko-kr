---
title: "지연 로드 된 DLL의 명시적 언로드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b26a1a17952693be9db6a80649aad2c40227d53e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>지연 로드된 DLL의 명시적 언로드
[지연/](../../build/reference/delay-delay-load-import-settings.md): unload 링커 옵션을 사용 하면 지연 로드 된 DLL을 언로드할 수 있습니다. 기본적으로 코드 DLL을 언로드할 때 (/delay: unload를 사용 하 여 및 **__FUnloadDelayLoadedDLL2**)을 지연 로드 가져오기 가져오기 주소 테이블 (IAT)에 유지 합니다. 그러나 /delay: unload 링커 명령줄에서를 사용 하는 도우미 함수가 지원 됩니다 원래 형태로; IAT를 다시 설정 하는 DLL의 명시적 언로드 지금은 적합 하지 않은 포인터를 덮어쓰게 됩니다. IAT는 필드는 [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) (있는 경우)의 원래 IAT 복사본의 주소를 포함 하 합니다.  
  
## <a name="example"></a>예  
  
### <a name="code"></a>코드  
  
```  
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD  
#include <windows.h>  
#include <delayimp.h>  
#include "MyDll.h"  
#include <stdio.h>  
  
#pragma comment(lib, "delayimp")  
#pragma comment(lib, "MyDll")  
int main()  
{  
    BOOL TestReturn;  
    // MyDLL.DLL will load at this point  
    fnMyDll();  
  
    //MyDLL.dll will unload at this point  
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");  
  
    if (TestReturn)  
        printf_s("\nDLL was unloaded");  
    else  
        printf_s("\nDLL was not unloaded");  
}  
```  
  
### <a name="comments"></a>설명  
 지연 로드 된 DLL 언로드에 중요 한 참고 사항:  
  
-   구현을 찾을 수 있습니다는 **__FUnloadDelayLoadedDLL2** 파일에서 함수 \VC7\INCLUDE\DELAYHLP 합니다. CPP 합니다.  
  
-   name 매개 변수는 **__FUnloadDelayLoadedDLL2** 함수 정확히 일치 해야 경우) (포함에 나타나는 내용을 가져오기 라이브러리 (문자열에에서 있는 이미지에 가져오기 테이블). 사용 하 여 가져오기 라이브러리 내용을 볼 수 있습니다 [/DEPENDENTS DUMPBIN](../../build/reference/dependents.md)합니다. 대/소문자 구분 문자열 일치를 사용 하는 필요한 경우 업데이트할 수 있습니다 **__FUnloadDelayLoadedDLL2** CRT 문자열 함수 또는 Windows API 호출 중 하나를 사용 합니다.  
  
 참조 [지연 로드 된 DLL 언로드](../../build/reference/unloading-a-delay-loaded-dll.md) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)