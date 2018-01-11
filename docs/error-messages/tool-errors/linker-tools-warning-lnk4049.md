---
title: "링커 도구 경고 LNK4049 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4049
dev_langs: C++
helpviewer_keywords: LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f44634bd99e485e444ffe9cee7747f31374becf4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4049"></a>링커 도구 경고 LNK4049
로컬 정의 클래스 가져온 ' symbol' 기호  
  
 기호에서 내보낸와 프로그램에 가져올 되었습니다.  
  
 사용 하 여 기호를 선언 하는 경우이 경고는 링커에서 발생는 `__declspec(dllexport)` 저장소 클래스를 하나의 개체 파일 특성을 사용 하 여 참조는 `__declspec(dllimport)` 다른 특성입니다.  
  
 보다 일반적인 버전이 경고 LNK4049 [링커 도구 경고 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)합니다. 링커 가져온된 기호가 참조 되는 함수를 확인할 수 없을 때 경고 LNK4049를 생성 합니다.  
  
 LNK4049 LNK4217 대신 여기서 생성 된 일반적인 경우가 있습니다.  
  
-   증분 링크를 사용 하 여 수행 된 [/incremental](../../build/reference/incremental-link-incrementally.md) 옵션입니다.  
  
-   전체 프로그램 최적화를 사용 하 여 수행 된 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) 옵션입니다.  
  
 LNK4049를 해결 하려면 다음 중 하나를 수행 합니다.  
  
-   제거는 `__declspec(dllimport)` LNK4049 트리거되는 기호의 정방향 선언에서 선언 이름을 지정 합니다. 이진 이미지 내에서 기호를 사용 하 여 검색할 수 있습니다는 **DUMPBIN** 유틸리티입니다. **DUMPBIN /SYMBOLS** 스위치 이미지의 COFF 기호 테이블을 표시 합니다. 대 한 자세한 내용은 **DUMPBIN** 유틸리티 참조 [DUMPBIN 참조](../../build/reference/dumpbin-reference.md)합니다.  
  
-   증분 링크 및 전체 프로그램 최적화를 일시적으로 비활성화 합니다. 응용 프로그램을 다시 컴파일하지 가져온된 기호 참조 함수의 이름이 포함 된 경고 LNK4217 생성 됩니다. 제거는 `__declspec(dllimport)` 가져온된 기호 및 증분 링크 사용 또는 필요에 따라 전체 프로그램 최적화를 선언 합니다.  
  
 마지막 생성 된 코드 올바르게 작동 하지만는 가져온된 함수를 호출 하도록 생성 된 코드 함수를 직접 호출 하는 보다 효율성이 떨어집니다. 옵션을 사용 하 여 컴파일하는 경우이 경고가 표시 되지 것입니다 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
 자세한 정보를 가져오고 내보내려면 데이터 선언에 대 한 참조 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)합니다.  
  
## <a name="example"></a>예  
 다음 두 개의 모듈 연결 LNK4049 생성 됩니다. 첫 번째 모듈 단일 내보낸된 함수를 포함 하는 개체 파일을 생성 합니다.  
  
```  
// LNK4049a.cpp  
// compile with: /c  
  
__declspec(dllexport) int func()   
{  
   return 3;  
}  
```  
  
## <a name="example"></a>예  
 두 번째 모듈 내에서이 함수를 호출 하는 첫 번째 모듈에서 내보낸 함수에 대 한 정방향 선언에 포함 된 개체 파일을 생성 된 `main` 함수입니다. 첫 번째 모듈을 사용 하 여이 모듈을 연결 하면 LNK4049 생성 됩니다. 제거는 `__declspec(dllimport)` 선언 하면 경고가 해결 됩니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [링커 도구 경고 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)