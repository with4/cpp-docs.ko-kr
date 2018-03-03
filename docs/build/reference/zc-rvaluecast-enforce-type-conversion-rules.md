---
title: "-Zc: rvalueCast (형식 변환 규칙 적용) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f4b888dde70708ee10b2d8000ff6380709dc870
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast(형식 변환 규칙 적용)
경우는 **/zc: rvaluecast** 옵션을 지정한 경우 컴파일러는 C + + 11 표준에 따라 캐스트 연산의 결과로 rvalue 참조 형식의 올바르게 식별 합니다. 이 옵션이 지정되지 않은 경우 컴파일러 동작은 Visual Studio 2012와 동일합니다. 기본적으로 **/zc: rvaluecast** 꺼져 있습니다. 준수 및 캐스트에서 오류를 제거 하기 위해 사용 하는 것이 좋습니다 **/zc: rvaluecast**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Zc:rvalueCast[-]  
```  
  
## <a name="remarks"></a>설명  
 경우 **/zc: rvaluecast** 이 지정 된 경우 컴파일러는 C + + 11 표준의 섹션 5.4에 따라 캐스트 비참조 형식 발생 하 고 비 함수 형식에 대 한 rvalue 참조에서 생성 하는 식을 캐스팅 하는 식만 처리 rvalue 형식입니다. 기본적으로 또는 **/Zc:rvalueCast-** 이 지정 된 경우 컴파일러는 비호환 적 모든 캐스트 식을 rvalue로 rvalue 참조에서 발생 하는 처리 합니다.  
  
 사용 하 여 **/zc: rvaluecast** rvalue 참조 형식을 사용 하는 함수에 캐스트 식을 인수로 전달 하는 경우. 기본 동작은 컴파일러 오류 [c 2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) 때 컴파일러 올바르게 형식을 잘못 결정 캐스트 식입니다. 다음 예제는 /Zc:rvalueCast를 지정하지 않은 경우 올바른 코드에서 발생한 컴파일러 오류를 보여줍니다.  
  
```cpp  
// Test of /Zc:rvalueCast  
// compile by using:  
// cl /c /Zc:rvalueCast- make_thing.cpp  
// cl /c /Zc:rvalueCast make_thing.cpp  
  
#include <utility>  
  
template <typename T>   
struct Thing {  
   // Construct a Thing by using two rvalue reference parameters  
   Thing(T&& t1, T&& t2)  
      : thing1(t1), thing2(t2) {}  
  
   T& thing1;  
   T& thing2;  
};  
  
// Create a Thing, using move semantics if possible  
template <typename T>  
Thing<T> make_thing(T&& t1, T&& t2)  
{  
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));  
}  
  
struct Test1 {  
   long a;  
   long b;  
  
   Thing<long> test() {   
      // Use identity casts to create rvalues as arguments  
      return make_thing(static_cast<long>(a), static_cast<long>(b));   
   }  
};  
  
```  
  
 보고하지 않는 것이 적절한 경우 기본 컴파일러 동작이 오류 C2102를 보고하지 않을 수도 있습니다. 이 예제에서는 컴파일러는 오류를 보고 하지 경우 id 캐스트에서 만든 rvalue 주소가 사용 되 면 **/zc: rvaluecast** 지정 되지 않았습니다.  
  
```cpp  
int main() {  
   int a = 1;  
   int *p = &a;   // Okay, take address of lvalue   
                  // Identity cast creates rvalue from lvalue;    
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value  
}  
```  
  
 Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **C/c + +** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  수정 된 **추가 옵션** 포함할 속성을 **/zc: rvaluecast** 선택한 후 **확인**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/Zc (규칙)](../../build/reference/zc-conformance.md)