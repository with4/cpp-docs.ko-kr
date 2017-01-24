---
title: "pack | Microsoft Docs"
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
  - "pack_CPP"
  - "vc-pragma.pack"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pack pragma"
  - "pragma, pack"
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pack
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

구조체, 공용 구조체 및 클래스 멤버에 대한 압축 맞춤을 지정합니다.  
  
## 구문  
  
```  
  
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )  
```  
  
## 설명  
 클래스를 압축하는 것은 해당 멤버를 메모리에서 서로 바로 뒤에 두는 것입니다. 이는 일부 또는 모든 멤버가 대상 아키텍처의 기본 맞춤보다 작은 경계에 정렬될 수 있음을 의미할 수 있습니다.  `pack`은 데이터 선언 수준에서 제어 기능을 제공합니다.  pack은 모듈 수준 제어 기능만 제공하는 [\/Zp](../build/reference/zp-struct-member-alignment.md) 컴파일러 옵션과 다릅니다.  `pack`은 pragma가 표시된 후 첫 번째 `struct`, `union` 또는 `class` 선언에서 적용됩니다.  `pack`은 정의에 아무런 영향을 주지 않습니다.  인수 없이 `pack`을 호출하면 `n`이 컴파일러 옵션 **\/Zp**에서 설정된 값으로 설정됩니다.  컴파일러 옵션이 설정되지 않은 경우 기본값은 8입니다.  
  
 구조체의 맞춤을 변경하는 경우 메모리에서 그만큼의 공간을 사용하지 않을 수 있지만, 성능이 저하되거나 정렬되지 않은 액세스에 대해 하드웨어에서 생성된 예외가 발생할 수도 있습니다.  [SetErrorMode](http://msdn.microsoft.com/library/windows/desktop/ms680621)를 사용하여 이 예외 동작을 수정할 수 있습니다.  
  
 **show** \(선택 사항\)  
 압축 맞춤에 대한 현재 바이트 값을 표시합니다.  경고 메시지에 값이 표시됩니다.  
  
 **push** \(선택 사항\)  
 내부 컴파일러 스택에 있는 현재 압축 맞춤 값을 푸시하고 현재 압축 맞춤 값을 `n`으로 설정합니다.  `n`을 지정하지 않으면 현재 압축 맞춤 값이 푸시됩니다.  
  
 **pop** \(선택 사항\)  
 내부 컴파일러 스택의 맨 위에서 레코드를 제거합니다.  `n`이 **pop**과 함께 지정되지 않은 경우 스택 맨 위의 결과 레코드와 연결된 압축 값이 새로운 압축 맞춤 값입니다.  `n`이 지정된 경우\(예: `#pragma pack(pop, 16)`\) `n`은 새로운 압축 맞춤 값이 됩니다.  `identifier`를 사용하여 팝하는 경우\(예: `#pragma pack(pop, r1)`\) `identifier`가 있는 레코드를 찾을 때까지 스택의 모든 레코드가 팝됩니다.  해당 레코드가 팝되고 스택 맨 위에 있는 결과 레코드와 연결된 압축 값이 새로운 압축 맞춤 값이 됩니다.  스택의 모든 레코드에 없는 `identifier`를 사용하여 팝하는 경우 **pop**이 무시됩니다.  
  
 `identifier` \(선택 사항\)  
 **push**와 함께 사용할 때 내부 컴파일러 스택의 레코드에 이름을 할당합니다.  **pop**과 함께 사용할 때 `identifier`가 제거될 때까지 내부 스택에서 레코드를 팝합니다. `identifier`가 내부 스택에 없으면 아무 것도 팝되지 않습니다.  
  
 `n`\(선택 사항\)  
 압축에 사용할 값\(바이트\)을 지정합니다.  컴파일러 옵션 [\/Zp](../build/reference/zp-struct-member-alignment.md)가 모듈에 대해 설정되지 않은 경우 `n`의 기본값은 8입니다.  유효한 값은 1, 2, 4, 8 및 16입니다.  멤버의 맞춤은 `n`의 배수나 멤버 크기의 배수 중 작은 것의 경계에 있습니다.  
  
 `#pragma pack(pop,` `identifier``,` `n``)`은 정의되어 있지 않습니다.  
  
 맞춤을 수정하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [\_\_alignof](../cpp/alignof-operator.md)  
  
-   [맞춤](../cpp/align-cpp.md)  
  
-   [\_\_unaligned](../cpp/unaligned.md)  
  
-   [구조체 맞춤 예제](../build/examples-of-structure-alignment.md)\(x64 전용\)  
  
    > [!WARNING]
    >  Visual Studio 2015 이상에서는 `__alignof` 및 `declspec( align )`와 달리 컴파일러 간에 이식 가능한 표준 alignas 및 alignof 연산자를 사용할 수 있습니다.  C\+\+ 표준에서는 압축을 처리하지 않으므로 대상 아키텍처의 단어 크기보다 작은 맞춤을 지정하려면 여전히 `pack` 또는 해당 확장\(다른 컴파일러\)을 사용해야 합니다.  
  
## 예제  
 다음 샘플에서는 `pack` pragma를 사용하여 구조체의 맞춤을 변경하는 방법을 보여 줍니다.  
  
```  
// pragma_directives_pack.cpp  
#include <stddef.h>  
#include <stdio.h>  
  
struct S {  
   int i;   // size 4  
   short j;   // size 2  
   double k;   // size 8  
};  
  
#pragma pack(2)  
struct T {  
   int i;  
   short j;  
   double k;  
};  
  
int main() {  
   printf("%zu ", offsetof(S, i));  
   printf("%zu ", offsetof(S, j));  
   printf("%zu\n", offsetof(S, k));  
  
   printf("%zu ", offsetof(T, i));  
   printf("%zu ", offsetof(T, j));  
   printf("%zu\n", offsetof(T, k));  
}  
```  
  
```  
0 4 8  
0 4 6  
```  
  
## 예제  
 다음 샘플에서는 **push**, **pop** 및 **show** 구문을 사용하는 방법을 보여 줍니다.  
  
```  
// pragma_directives_pack_2.cpp  
// compile with: /W1 /c  
#pragma pack()   // n defaults to 8; equivalent to /Zp8  
#pragma pack(show)   // C4810  
#pragma pack(4)   // n = 4  
#pragma pack(show)   // C4810  
#pragma pack(push, r1, 16)   // n = 16, pushed to stack  
#pragma pack(show)   // C4810  
#pragma pack(pop, r1, 2)   // n = 2 , stack popped  
#pragma pack(show)   // C4810  
```  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)