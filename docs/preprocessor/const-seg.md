---
title: "const_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.const_seg"
  - "const_seg_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_seg pragma"
  - "pragma, const_seg"
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# const_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.obj 파일에서 [const](../cpp/const-cpp.md) 변수가 저장되는 세그먼트를 지정합니다.  
  
## 구문  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## 설명  
 *세그먼트* 및 *섹션*의 의미는 이 항목에서 동일하게 사용됩니다.  
  
 OBJ 파일은 [dumpbin](../build/reference/dumpbin-command-line.md) 응용 프로그램으로 볼 수 있습니다.  `const` 변수에 대한 .obj 파일의 기본 세그먼트는 .rdata입니다.  스칼라 같은 일부 `const` 변수는 자동으로 코드 스트림으로 인라인 처리됩니다.  인라인 처리된 코드는 .rdata에 나타나지 않습니다.  
  
 `const_seg`에 동적 초기화가 필요한 개체를 정의하면 정의되지 않은 동작이 발생합니다.  
  
 매개 변수 없는 `#pragma const_seg`는 세그먼트를 .rdata로 다시 설정합니다.  
  
 `push`\(선택 사항\)  
 내부 컴파일러 스택에 기록합니다.  `push`에는 `identifier` 및 `segment-name`이 포함될 수 있습니다.  
  
 `pop`\(선택 사항\)  
 내부 컴파일러 스택 맨 위에서 기록을 제거합니다.  
  
 `identifier`\(선택 사항\)  
 `push`와 함께 사용할 때 내부 컴파일러 스택의 레코드에 이름을 할당합니다.  `pop`과 함께 사용할 때 `identifier`가 제거될 때까지 내부 스택에서 레코드를 팝합니다. `identifier`가 내부 스택에 없으면 아무 것도 팝되지 않습니다.  
  
 `identifier`를 사용하면 여러 레코드가 하나의 `pop` 명령으로 팝될 수 있습니다.  
  
 "`segment-name`"\(옵션\)  
 세그먼트의 이름입니다.  스택은 `pop`과 함께 사용하면 팝되고 `segment-name`이 활성 세그먼트 이름이 됩니다.  
  
 "`segment-class`"\(옵션\)  
 C\+\+ 2.0 이전 버전과의 호환성을 위해 포함됩니다.  무시됩니다.  
  
## 예제  
  
```  
// pragma_directive_const_seg.cpp  
// compile with: /EHsc  
#include <iostream>  
  
const int i = 7;               // inlined, not stored in .rdata  
const char sz1[]= "test1";     // stored in .rdata  
  
#pragma const_seg(".my_data1")  
const char sz2[]= "test2";     // stored in .my_data1  
  
#pragma const_seg(push, stack1, ".my_data2")  
const char sz3[]= "test3";     // stored in .my_data2  
  
#pragma const_seg(pop, stack1) // pop stack1 from stack  
const char sz4[]= "test4";     // stored in .my_data1  
  
int main() {  
    using namespace std;  
   // const data must be referenced to be put in .obj  
   cout << sz1 << endl;  
   cout << sz2 << endl;  
   cout << sz3 << endl;  
   cout << sz4 << endl;  
}  
```  
  
  **테스트 1**  
**테스트 2**  
**테스트 3**  
**테스트 4**   
## 메모  
 섹션을 만들 때 사용할 수 없는 이름 목록은 [\/SECTION](../build/reference/section-specify-section-attributes.md)을 참조하십시오.  
  
 초기화된 데이터\([data\_seg](../preprocessor/data-seg.md)\), 초기화 되지 않는 데이터\([bss\_seg](../preprocessor/bss-seg.md)\) 및 함수\([code\_seg](../preprocessor/code-seg.md)\)에 대한 섹션을 지정할 수 있습니다.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)