---
title: const_seg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c4c87ee9f0e867223186868de0ef2b39203c3710
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="constseg"></a>const_seg
세그먼트를 지정 합니다. 여기서 [const](../cpp/const-cpp.md) 변수가.obj 파일에 저장 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>설명  
 의미 *세그먼트* 및 *섹션* 은이 항목의 서로 전환이 가능 합니다.  
  
 OBJ 파일을 볼 수 있는 [dumpbin](../build/reference/dumpbin-command-line.md) 응용 프로그램입니다. `const` 변수에 대한 .obj 파일의 기본 세그먼트는 .rdata입니다. 스칼라 같은 일부 `const` 변수는 자동으로 코드 스트림으로 인라인 처리됩니다. 인라인 처리된 코드는 .rdata에 나타나지 않습니다.  
  
 `const_seg`에 동적 초기화가 필요한 개체를 정의하면 정의되지 않은 동작이 발생합니다.  
  
 매개 변수 없는 `#pragma const_seg`는 세그먼트를 .rdata로 다시 설정합니다.  
  
 `push`(선택 사항)  
 내부 컴파일러 스택에 기록합니다. `push`에는 `identifier` 및 `segment-name`이 포함될 수 있습니다.  
  
 `pop`(선택 사항)  
 내부 컴파일러 스택 맨 위에서 기록을 제거합니다.  
  
 `identifier`(선택 사항)  
 `push`와 함께 사용할 때 내부 컴파일러 스택의 레코드에 이름을 할당합니다. `pop`과 함께 사용할 때 `identifier`가 제거될 때까지 내부 스택에서 레코드를 팝합니다. `identifier`가 내부 스택에 없으면 아무 것도 팝되지 않습니다.  
  
 `identifier`를 사용하면 여러 레코드가 하나의 `pop` 명령으로 팝될 수 있습니다.  
  
 "`segment-name`"(옵션)  
 세그먼트의 이름입니다. 스택은 `pop`과 함께 사용하면 팝되고 `segment-name`이 활성 세그먼트 이름이 됩니다.  
  
 "`segment-class`"(옵션)  
 C++ 2.0 이전 버전과의 호환성을 위해 포함됩니다. 무시됩니다.  
  
## <a name="example"></a>예  
  
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
  
```Output  
test1  
test2  
test3  
test4  
```  
  
## <a name="comments"></a>설명  
 참조 [/section](../build/reference/section-specify-section-attributes.md) 섹션을 만들 때 사용 하지 않아야 하는 이름 목록에 대 한 합니다.  
  
 초기화 된 데이터에 대 한 섹션도 지정할 수 있습니다 ([data_seg](../preprocessor/data-seg.md)), 초기화 되지 않은 데이터 ([bss_seg](../preprocessor/bss-seg.md)), 및 함수 ([code_seg](../preprocessor/code-seg.md)).  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)