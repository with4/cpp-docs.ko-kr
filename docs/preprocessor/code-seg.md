---
title: code_seg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
dev_langs:
- C++
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f958d1652f82f297ae530c1e24bdf331976e0dc0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839075"
---
# <a name="codeseg"></a>code_seg
함수가 .obj 파일에 저장되는 텍스트 세그먼트를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>설명  
 `code_seg` pragma 지시문은 인스턴스화된 템플릿에 대해 생성된 개체 코드와 특수 멤버 함수 등 컴파일러로 암시적으로 생성된 코드의 배치를 제어하지 않습니다. 사용 하는 것이 좋습니다는 [code_seg ](../cpp/code-seg-declspec.md) 수 있기 때문에 특성을 대신 모든 개체 코드의 배치에 대해 제어 합니다. 여기에는 컴파일러에서 생성된 코드가 포함됩니다.  
  
 A *세그먼트* .obj 파일은 하나의 단위로 메모리에 로드 되는 데이터의 명명 된 블록입니다. A *텍스트 세그먼트* 실행 코드가 포함 된 세그먼트입니다. 이 문서의 내용 *세그먼트* 및 *섹션* 같은 의미로 사용 됩니다.  
  
 `code_seg` pragma 지시문은 변환 단위의 모든 이후의 개체 코드를 `segment-name`라는 텍스트 세그먼트로 배치하도록 컴파일러에 지시합니다. 기본적으로 .obj 파일의 함수에 사용되는 텍스트 세그먼트는 .text로 명명됩니다.  
  
 매개 변수가 없는 `code_seg` pragma 지시문은 이후 개체 코드의 텍스트 세그먼트 이름을 .text로 다시 설정합니다.  
  
 **푸시** (선택 사항)  
 내부 컴파일러 스택에 기록합니다. A **푸시** 가질 수 있습니다는 `identifier` 및 `segment-name`합니다.  
  
 **pop** (선택 사항)  
 내부 컴파일러 스택 맨 위에서 기록을 제거합니다.  
  
 `identifier`(선택 사항)  
 와 함께 사용할 경우 **푸시**, 내부 컴파일러 스택의 레코드에 이름을 할당 합니다. 와 함께 사용할 경우 **pop**, 될 때까지 내부 스택에서 레코드를 팝 `identifier` 가 제거 `identifier` 에 없는 내부 스택에서 아무 것도 팝 합니다.  
  
 `identifier` 여러 레코드 하나만으로 팝 될 수 있습니다 **pop** 명령입니다.  
  
 "`segment-name`"(옵션)  
 세그먼트의 이름입니다. 와 함께 사용할 경우 **pop**, 스택을 팝 되 고 `segment-name` 활성 텍스트 세그먼트 이름이 됩니다.  
  
 "`segment-class`"(옵션)  
 무시되지만 2.0 이전 버전의 C++ 버전과의 호환성을 위해 포함되었습니다.  
  
 사용할 수는 [DUMPBIN 합니다. EXE](../build/reference/dumpbin-command-line.md) .obj 파일을 보려면 응용 프로그램입니다. 지원되는 각 대상 아키텍처의 DUMPBIN 버전은 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에 포함되어 있습니다.  
  
## <a name="example"></a>예제  
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
  
 섹션을 만들 안되며 이름 목록은 참조 하십시오. [/section](../build/reference/section-specify-section-attributes.md)합니다.  
  
 초기화 된 데이터에 대 한 섹션도 지정할 수 있습니다 ([data_seg](../preprocessor/data-seg.md)), 초기화 되지 않은 데이터 ([bss_seg](../preprocessor/bss-seg.md)), 및 상수 변수 ([const_seg](../preprocessor/const-seg.md)).  
  
## <a name="see-also"></a>참고 항목  
 [code_seg (__declspec)](../cpp/code-seg-declspec.md)   
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)