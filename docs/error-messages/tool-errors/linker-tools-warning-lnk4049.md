---
title: "링커 도구 경고 LNK4049 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4049"
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# 링커 도구 경고 LNK4049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지역으로 정의된 기호 'symbol'을\(를\) 가져왔습니다.  
  
 기호를 프로그램에 내보낸 다음에 프로그램에서 가져왔습니다.  
  
 이 경고는 개체 파일 중 하나에서 `__declspec(dllexport)` 저장소 클래스 특성을 사용하여 기호를 선언하고 다른 파일에서 `__declspec(dllimport)` 특성을 사용하여 기호를 참조한 경우 링커에서 발생합니다.  
  
 LNK4049 경고는 보다 일반적인 버전의 [링커 도구 경고 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)입니다.  링커에서는 가져온 기호가 참조되는 함수를 확인할 수 없는 경우 LNK4049 경고가 발생합니다.  
  
 LNK4217 대신 LNK4049가 발생하는 일반적인 경우는 다음과 같습니다.  
  
-   [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) 옵션을 사용하여 증분 링크 수행  
  
-   [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) 옵션을 사용하여 전체 프로그램 최적화 수행  
  
 LNK4049를 해결하려면 다음 중 하나를 수행하십시오.  
  
-   LNK4049가 발생한 기호의 전방 선언에서 `__declspec(dllimport)` 이름 선언을 제거합니다.  **DUMPBIN** 유틸리티를 사용하여 이진 이미지 내에서 기호를 찾을 수 있습니다.  **DUMPBIN \/SYMBOLS** 스위치를 사용하면 이미지의 COFF 기호 테이블이 표시됩니다.  **DUMPBIN** 유틸리티에 대한 자세한 내용은 [DUMPBIN 참조](../../build/reference/dumpbin-reference.md)를 참조하십시오.  
  
-   증분 링크 및 전체 프로그램 최적화를 임시로 해제합니다.  응용 프로그램을 다시 컴파일하면 LNK4217 경고가 발생하며, 가져온 기호가 참조된 함수 이름이 함께 표시됩니다.  가져온 기호에서 `__declspec(dllimport)` 선언을 제거하고 필요에 따라 증분 링크나 전체 프로그램 최적화를 활성화하십시오.  
  
 생성된 최종 코드는 정상적으로 작동하지만, 가져온 함수를 호출하도록 생성된 코드는 함수를 직접 호출하는 코드보다 효율성이 낮습니다.  [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 사용하여 컴파일하는 경우에는 이 경고가 표시되지 않습니다.  
  
 데이터 선언 가져오기 및 내보내기에 대한 자세한 내용은 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)를 참조하십시오.  
  
## 예제  
 다음 두 모듈을 링크하면 LNK4049가 발생합니다.  첫 번째 모듈에서는 내보낸 함수 하나가 들어 있는 개체 파일을 생성합니다.  
  
```  
// LNK4049a.cpp  
// compile with: /c  
  
__declspec(dllexport) int func()   
{  
   return 3;  
}  
```  
  
## 예제  
 두 번째 모듈에서는 첫 번째 모듈에서 내보낸 함수에 대한 전방 선언이 들어 있는 개체 파일을 생성하며, `main` 함수 내에서 이 함수를 호출합니다.  이 모듈을 첫 번째 모듈과 링크하면 LNK4049가 발생합니다.  `__declspec(dllimport)` 선언을 제거하면 경고가 해결됩니다.  
  
```  
// LNK4049b.cpp  
// compile with: /link /WX /LTCG LNK4049a.obj  
// LNK4049 expected  
  
__declspec(dllimport) int func();  
// try the following line instead  
// int func();  
  
int main()  
{  
   return func();  
}  
```  
  
## 참고 항목  
 [링커 도구 경고 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)