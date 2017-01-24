---
title: "__uuidof 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__LIBID_"
  - "__LIBID_cpp"
  - "__uuidof"
  - "__uuidof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__LIBID_ 키워드[C++]"
  - "__uuidof 키워드[C++]"
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __uuidof 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 식에 연결된 GUID를 검색합니다.  
  
## 구문  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## 설명  
 *식*은 형식 이름, 포인터, 참조 또는 배열 형식, 이러한 형식의 변수 또는 형식에 특화된 템플릿이 될 수 있습니다.  인수가 유효하면 컴파일러는 연결된 GUID를 인수를 사용하여 찾을 수 있습니다.  
  
 이 내장의 특수 한 경우는 다음 경우 중 하나 **0** 또는 **NULL** 인수로 제공 됩니다.  이 경우, `__uuidof` 는 0으로 구성 된 GUID를 반환합니다.  
  
 이 키워드를 사용하여 연결된 GUID를 추출하려면:  
  
-   확장된 특성 [uuid](../cpp/uuid-cpp.md) 에 의한 개체입니다.  
  
-   [모듈](../windows/module-cpp.md) 특성을 사용하여 만든 라이브러리 블록입니다.  
  
> [!NOTE]
>  디버그 빌드에서 `__uuidof` 는 항상 동적으로 \(런타임에서\) 개체를 초기화합니다.  릴리스 빌드에서, `__uuidof` 는 정적으로 \(컴파일 타임에서\) 개체를 초기화할 수 있습니다.  
  
## 예제  
 \(ole.32lib를 사용하여 컴파일된\) 다음 코드는 Module 특성을 사용하여 만든 블록 라이브러리의 uuid를 표시합니다.  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## 설명  
 라이브러리가 더 이상 범위에 없는 경우에서 \_\_LIBID\_를 `__uuidof` 대신에 사용할 수 없습니다.  예를 들면 다음과 같습니다.  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)