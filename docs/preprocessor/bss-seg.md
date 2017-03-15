---
title: "bss_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.bss_seg"
  - "bss_seg_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bss_seg pragma"
  - "pragma, bss_seg"
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# bss_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.obj 파일에 초기화되지 않은 변수가 저장되는 세그먼트를 지정합니다.  
  
## 구문  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## 설명  
 Obj 파일은 [dumpbin](../build/reference/dumpbin-command-line.md) 응용 프로그램으로 볼 수 있습니다.  초기화되지 않은 데이터에 대한 .obj 파일의 기본 세그먼트는 .bss입니다.  경우에 따라 **bss\_seg**를 사용하면 초기화되지 않은 데이터를 한 세그먼트로 그룹화하여 로드 시간을 앞당길 수 있습니다.  
  
 매개 변수 없는 **bss\_seg**는 세그먼트를 .bss로 다시 설정합니다.  
  
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
// pragma_directive_bss_seg.cpp  
int i;                     // stored in .bss  
#pragma bss_seg(".my_data1")  
int j;                     // stored in "my_data1"  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;                     // stored in "my_data2"  
  
#pragma bss_seg(pop, stack1)   // pop stack1 from stack  
int m;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 또한 초기화된 데이터\([data\_seg](../preprocessor/data-seg.md)\), 함수\([code\_seg](../preprocessor/code-seg.md)\) 및 상수 변수\([const\_seg](../preprocessor/const-seg.md)\)에 대한 섹션을 지정할 수 있습니다.  
  
 **bss\_seg** pragma를 사용하여 할당한 데이터는 위치에 대한 정보를 보존하지 않습니다.  
  
 섹션을 만들 때 사용할 수 없는 이름 목록은 [\/SECTION](../build/reference/section-specify-section-attributes.md)을 참조하십시오.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)