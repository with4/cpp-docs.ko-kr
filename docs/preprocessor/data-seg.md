---
title: "data_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "data_seg_CPP"
  - "vc-pragma.data_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "data_seg pragma"
  - "pragma, data_seg"
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# data_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

초기화된 변수가 .obj 파일에 저장되는 데이터 세그먼트를 지정합니다.  
  
## 구문  
  
```  
  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## 설명  
 *세그먼트* 및 *섹션*의 의미는 이 항목에서 동일하게 사용됩니다.  
  
 OBJ 파일은 [dumpbin](../build/reference/dumpbin-command-line.md) 응용 프로그램으로 볼 수 있습니다.  초기화된 변수에 대한 .obj 파일의 기본 세그먼트는 .data입니다.  초기화되지 않은 변수는 0으로 초기화된 것으로 간주되고 .bss에 저장됩니다.  
  
 매개 변수가 없는 **data\_seg**는 세그먼트를 .data로 다시 설정합니다.  
  
 **push**\(선택 사항\)  
 내부 컴파일러 스택에 기록합니다.  **push**에는 식별자와 세그먼트 이름이 포함될 수 있습니다.  
  
 **pop**\(선택 사항\)  
 내부 컴파일러 스택 맨 위에서 기록을 제거합니다.  
  
 식별자\(선택 사항\)  
 **push**와 함께 사용하여 내부 컴파일러 스택의 기록에 이름을 할당합니다.  **pop**과 함께 사용하면, 식별자가 제거될 때까지 내부 스택에서 기록을 팝합니다. 식별자가 내부 스택에 없다면, 아무것도 나오지 않습니다.  
  
 *identifier*를 사용하면 단일 **pop** 명령으로 여러 레코드를 팝할 수 있습니다.  
  
 "세그먼트 이름"\(선택 사항\)  
 세그먼트의 이름입니다*.* **pop**과 함께 사용하면 스택이 팝되고 세그먼트 이름은 활성 세그먼트 이름이 됩니다.  
  
 "세그먼트 클래스"\(선택 사항\)  
 C\+\+ 2.0 이전 버전과의 호환성을 위해 포함됩니다.  무시됩니다.  
  
## 예제  
  
```  
// pragma_directive_data_seg.cpp  
int h = 1;                     // stored in .data  
int i = 0;                     // stored in .bss  
#pragma data_seg(".my_data1")  
int j = 1;                     // stored in "my_data1"  
  
#pragma data_seg(push, stack1, ".my_data2")     
int l = 2;                     // stored in "my_data2"  
  
#pragma data_seg(pop, stack1)   // pop stack1 off the stack  
int m = 3;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 **data\_seg**를 사용하여 할당한 데이터는 위치에 대한 정보를 보존하지 않습니다.  
  
 섹션을 만들 때 사용할 수 없는 이름 목록은 [\/SECTION](../build/reference/section-specify-section-attributes.md)을 참조하십시오.  
  
 상수 변수\([const\_seg](../preprocessor/const-seg.md)\), 초기화되지 않은 데이터\([bss\_seg](../preprocessor/bss-seg.md)\) 및 함수\([code\_seg](../preprocessor/code-seg.md)\)에 대한 섹션도 지정할 수 있습니다.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)