---
title: "code_seg | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "code_seg_CPP"
  - "vc-pragma.code_seg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "code_seg pragma"
  - "pragma, code_seg"
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# code_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수가 .obj 파일에 저장되는 텍스트 세그먼트를 지정합니다.  
  
## 구문  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## 설명  
 `code_seg` pragma 지시문은 인스턴스화된 템플릿에 대해 생성된 개체 코드와 특수 멤버 함수 등 컴파일러로 암시적으로 생성된 코드의 배치를 제어하지 않습니다.  대신에 모든 개체 코드의 배치에 대해 제어를 할 수 있는 [\_\_declspec\(code\_seg\(...\)\)](../cpp/code-seg-declspec.md) 특성을 사용하는 것이 좋습니다.  여기에는 컴파일러에서 생성된 코드가 포함됩니다.  
  
 .obj 파일의 *세그먼트*는 메모리에 하나의 단위로 로드된 명명된 데이터 블록입니다.  *텍스트 세그먼트*는 실행 코드가 포함된 세그먼트입니다.  이 문서에서 *세그먼트* 및 *섹션*이라는 용어는 같은 의미로 사용됩니다.  
  
 `code_seg` pragma 지시문은 변환 단위의 모든 이후의 개체 코드를 `segment-name`라는 텍스트 세그먼트로 배치하도록 컴파일러에 지시합니다.  기본적으로 .obj 파일의 함수에 사용되는 텍스트 세그먼트는 .text로 명명됩니다.  
  
 매개 변수가 없는 `code_seg` pragma 지시문은 이후 개체 코드의 텍스트 세그먼트 이름을 .text로 다시 설정합니다.  
  
 **Push**\(선택적 요소\)  
 내부 컴파일러 스택에 기록합니다.  **push**에는 `identifier` 및 `segment-name`이 포함될 수 있습니다.  
  
 **pop**\(선택적 요소\)  
 내부 컴파일러 스택 맨 위에서 기록을 제거합니다.  
  
 `identifier`\(선택적 요소\)  
 **push**와 함께 사용할 때 내부 컴파일러 스택의 레코드에 이름을 할당합니다.  **pop**과 함께 사용할 때 `identifier`가 제거될 때까지 내부 스택에서 레코드를 팝합니다. `identifier`가 내부 스택에 없으면 아무 것도 팝되지 않습니다.  
  
 `identifier`를 사용하면 여러 레코드가 하나의 **pop** 명령으로 팝될 수 있습니다.  
  
 "`segment-name`"\(옵션\)  
 세그먼트의 이름입니다.  스택은 **pop**과 함께 사용하면 팝되고 `segment-name`이 활성 텍스트 세그먼트 이름이 됩니다.  
  
 "`segment-class`"\(옵션\)  
 무시되지만 2.0 이전 버전의 C\+\+ 버전과의 호환성을 위해 포함되었습니다.  
  
 [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) 응용 프로그램을 사용하여 .obj 파일을 볼 수 있습니다.  지원되는 각 대상 아키텍처의 DUMPBIN 버전은 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에 포함되어 있습니다.  
  
## 예제  
 이 예제에서는 `code_seg` pragma 지시문을 사용하여 개체 코드를 배치하는 위치를 제어하는 방법을 보여 줍니다.  
  
```  
// pragma_directive_code_seg.cpp  
void func1() {                  // stored in .text  
}  
  
#pragma code_seg(".my_data1")  
void func2() {                  // stored in my_data1  
}  
  
#pragma code_seg(push, r1, ".my_data2")  
void func3() {                  // stored in my_data2  
}  
  
#pragma code_seg(pop, r1)      // stored in my_data1  
void func4() {  
}  
  
int main() {  
}  
```  
  
 섹션을 만들 때 사용할 수 없는 이름 목록은 [\/SECTION](../build/reference/section-specify-section-attributes.md)을 참조하십시오.  
  
 초기화된 데이터\([data\_seg](../preprocessor/data-seg.md)\), 초기화되지 않은 데이터\([bss\_seg](../preprocessor/bss-seg.md)\) 및 상수 변수\([const\_seg](../preprocessor/const-seg.md)\)에 대한 섹션도 지정할 수 있습니다.  
  
## 참고 항목  
 [code\_seg \(\_\_declspec\)](../cpp/code-seg-declspec.md)   
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)