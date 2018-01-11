---
title: bss_seg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0dd1e24127129ef833cfd4906085eabbf1e5c380
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bssseg"></a>bss_seg
.obj 파일에 초기화되지 않은 변수가 저장되는 세그먼트를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>설명  
 Obj 파일을 볼 수 있는 [dumpbin](../build/reference/dumpbin-command-line.md) 응용 프로그램입니다. 초기화되지 않은 데이터에 대한 .obj 파일의 기본 세그먼트는 .bss입니다. 경우에 따라 사용 **bss_seg** 속도 높일 수를 한 초기화 되지 않은 데이터를 그룹화 하 여 로드 시간입니다.  
  
 **bss_seg** 매개 변수 없이 세그먼트를.bss 다시 설정 합니다.  
  
 **푸시**(선택 사항)  
 내부 컴파일러 스택에 기록합니다. A **푸시** 가질 수 있습니다는 *식별자* 및 *세그먼트 이름*합니다.  
  
 **pop** (선택 사항)  
 내부 컴파일러 스택 맨 위에서 기록을 제거합니다.  
  
 *식별자* (선택 사항)  
 와 함께 사용할 경우 **푸시**, 내부 컴파일러 스택의 레코드에 이름을 할당 합니다. 와 함께 사용할 경우 **pop**, 될 때까지 내부 스택에서 레코드를 팝 *식별자* 가 제거 *식별자* 에 없는 내부 스택에서 아무 것도 팝 합니다.  
  
 *식별자* 여러 레코드는 단일으로 팝 될 수 있습니다 **pop** 명령입니다.  
  
 *"세그먼트 이름"*(선택 사항)  
 세그먼트의 이름입니다. 와 함께 사용할 경우 **pop**, 스택을 팝 되 고 *세그먼트 이름* 활성 세그먼트 이름이 됩니다.  
  
 *"세그먼트 클래스"* (선택 사항)  
 C++ 2.0 이전 버전과의 호환성을 위해 포함됩니다. 무시됩니다.  
  
## <a name="example"></a>예  
  
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
  
 초기화 된 데이터에 대 한 섹션도 지정할 수 있습니다 ([data_seg](../preprocessor/data-seg.md)), 함수 ([code_seg](../preprocessor/code-seg.md)), 및 상수 변수 ([const_seg](../preprocessor/const-seg.md)).  
  
 사용 하 여 할당 된 데이터는 **bss_seg** pragma의 위치에 대 한 정보를 유지 하지 않습니다.  
  
 참조 [/section](../build/reference/section-specify-section-attributes.md) 섹션을 만들 때 사용 하지 않아야 하는 이름 목록에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)