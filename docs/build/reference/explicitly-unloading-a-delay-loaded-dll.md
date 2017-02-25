---
title: "지연 로드된 DLL의 명시적 언로드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY:UNLOAD 링커 옵션"
  - "__FUnloadDelayLoadedDLL2"
  - "DELAY:UNLOAD 링커 옵션"
  - "지연 DLL 로드, 언로드"
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 지연 로드된 DLL의 명시적 언로드
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링커 옵션 [\/DELAY](../../build/reference/delay-delay-load-import-settings.md):unload를 사용하면 지연 로드된 DLL을 언로드할 수 있습니다.  기본적으로 코드에서 \/delay:unload 및 **\_\_FUnloadDelayLoadedDLL2**를 사용하여 DLL을 언로드하면 지연 로드된 가져오기가 IAT\(가져오기 주소 테이블\)에 남게 됩니다.  그러나 링커 명령줄에서 \/delay:unload를 사용하면 도우미 함수가 DLL의 명시적인 언로드를 지원하면서 IAT를 원래의 형태로 다시 설정하게 되므로 현재 유효하지 않은 포인터를 덮어쓰게 됩니다.  IAT는 원본 IAT의 복사본이 있는 경우 해당 주소를 포함하는 [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md)의 필드입니다.  
  
## 예제  
  
### 코드  
  
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
  
### 설명  
 지연 로드된 DLL을 언로드할 때의 유의 사항  
  
-   **\_\_FUnloadDelayLoadedDLL2** 함수는 \\VC7\\INCLUDE\\DELAYHLP.CPP 파일에 구현됩니다.  
  
-   **\_\_FUnloadDelayLoadedDLL2** 함수의 name 매개 변수는 가져오기 라이브러리의 내용과 일치해야 합니다\(대\/소문자 여부 포함\). 즉, 해당 문자열이 이미지의 가져오기 테이블에도 있어야 합니다.  [DUMPBIN \/DEPENDENTS](../../build/reference/dependents.md)를 사용하여 가져오기 라이브러리의 내용을 볼 수 있습니다.  대\/소문자를 구분하지 않는 문자열 일치가 필요하면 **\_\_FUnloadDelayLoadedDLL2**를 업데이트하여 CRT 문자열 함수 중 하나나 Windows API 호출을 사용할 수 있습니다.  
  
 자세한 내용은 [지연 로드된 DLL 언로드](../../build/reference/unloading-a-delay-loaded-dll.md)를 참조하십시오.  
  
## 참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)