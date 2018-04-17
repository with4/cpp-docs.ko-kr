---
title: 문자열 리터럴이 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- string literals
- strings [C++], string literals
ms.assetid: 6d1fc3f8-0d58-4d68-9678-16b4f6dc4766
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd62f85b87473d1371daf2d2fa009d8620e59b57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="string-literal"></a>문자열 리터럴
문자열 리터럴 처리의 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 문자열 리터럴을 앞으로 지정 된 관리 되는 문자열 리터럴을 Managed extensions for c + + 언어 디자인은 `S`합니다. 예:  
  
```  
String *ps1 = "hello";  
String *ps2 = S"goodbye";  
```  
  
 결과적으로 특수는 사이의 성능 오버 헤드는 두 번의 초기화,으로 다음 CIL 표현을 보여 줍니다 차례로 살펴 보았을 때 **ildasm**:  
  
```  
// String *ps1 = "hello";  
ldsflda    valuetype $ArrayType$0xd61117dd  
     modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier)   
     '?A0xbdde7aca.unnamed-global-0'  
  
newobj instance void [mscorlib]System.String::.ctor(int8*)  
stloc.0  
  
// String *ps2 = S"goodbye";  
ldstr      "goodbye"  
stloc.0  
```  
  
 방금 기억 (또는 학습)는 리터럴 문자열 접두사를 지정 하는 뛰어난 절감 비율이입니다는 `S`합니다. 새 구문에서 사용 하 여 컨텍스트에서 확인 된 문자열 리터럴 처리 투명 하 게 구성 됩니다. `S` 더 이상 지정 해야 합니다.  
  
 어떤 점이 있는 해야 명시적으로 하는 경우에는 컴파일러 특정 해석을에 지시할? 이러한 경우에 명시적 캐스트가 적용 했습니다. 예:  
  
```  
f( safe_cast<String^>("ABC") );  
```  
  
 또한, 리터럴 문자열은 이제는 `String` 표준 변환이 아닌 간단한 변환을 사용 합니다. 이렇게 하지 같지만 포함 하는 오버 로드 된 함수 집합의 해상도 변경 하기는 훨씬 동안는 `String` 및 `const char*` 경쟁 정식 매개 변수로 서 합니다. 이전에 해상도 `const char*` 인스턴스는 이제 모호한 것으로 표시 됩니다. 예:  
  
```  
ref struct R {  
   void f(const char*);  
   void f(String^);  
};  
  
int main () {  
   R r;  
   // old syntax: f( const char* );  
   // new syntax: error: ambiguous  
   r.f("ABC");   
}  
```  
  
 차이가 있는 이유는 무엇입니까? 명명 된 인스턴스가 둘 이상 이후 `f` 존재 호출에 적용 될 함수 오버 로드 확인 알고리즘이 프로그램에서 필요 합니다. 오버 로드 함수의 형식 확인은 세 단계로 진행 됩니다.  
  
1.  후보 함수의 컬렉션입니다. 후보 함수 어휘 적으로 호출 하는 함수 이름을 일치 하는 범위 내에서 이러한 메서드는 합니다. 예를 들어 이후 `f()` 의 인스턴스를 통해 호출 되 `R`모든 명명 된 함수 `f` 의 맴버가 아닌 `R` (또는 해당 기본 클래스 계층) 후보 함수 되지 않습니다. 예제에서는 두 개의 후보 함수도 있습니다. 두 명의 멤버 함수는 `R` 라는 `f`합니다. 후보 함수 집합이 비어 있으면이 단계는 호출이 실패 합니다.  
  
2.  후보 함수 중에서 사용 가능한 함수 집합입니다. 가능한 함수는 인수 및 형식 수가 제공 되는 호출에 지정 된 인수를 사용 하 여 호출 수입니다. 예제에서는 두 후보 함수는 모두 사용 가능한 함수입니다. 사용 가능한 함수 집합이 비어 있으면이 단계는 호출이 실패 합니다.  
  
3.  가장 일치 하는 호출을 나타내는 함수를 선택 합니다. 이 순위 가능한 함수 매개 변수의 형식에 대 한 인수를 변환에 적용 되는 변환 하 여 수행 됩니다. 이 비교적 간단 단일 매개 변수 함수로 여러 매개 변수가 있는 경우 다소 복잡 한 됩니다. 가장 일치 하는 경우이 단계는 호출이 실패 합니다. 즉, 형식 매개 변수 형식의 실제 인수의 형식을 변환 하는 데 필요한 변환에 동일 하는 경우. 호출 모호한 것으로 플래그가 지정 됩니다.  
  
 Managed extensions를 호출 하는이 호출의 해상도 `const char*` 최상의 일치로 인스턴스. 새 구문에서 일치 하는 데 필요한 변환 `"abc"` 를 `const char*` 및 `String^` 동일 이제-즉, 동등-호출으로 플래그가 지정 되어 잘못 된-즉, 있으므로 모호한 것으로 합니다.  
  
 이 두 가지 질문을 안내 합니다.  
  
-   실제 인수의 유형을 `"abc"`?  
  
-   형식 변환 다른 보다 더 나은 경우 결정 하기 위한 알고리즘은 무엇입니까?  
  
 리터럴 문자열의 유형을 `"abc"` 은 `const char[4]` -리터럴 모든 문자열의 끝에 암시적 null 종결 문자입니다.  
  
 다른 보다 더 나은 형식 변환 되었는지 확인 하는 알고리즘이 가능한 형식 변환 계층에 배치 하는 작업이 포함 됩니다. 다음은 지식 해당 계층의 모든이 변환은 물론,는 암시적 합니다. 계층 구조 방식과 유사 하 게 재정의 명시적 캐스트 표기법을 사용 하 여 괄호 식의 일반적인 연산자 우선 순위를 재정의 합니다.  
  
1.  정확히 일치 하는 것이 가장 좋습니다. 놀랍게도 정확 하 게 일치 하는 인수에 대 한 하지 않아도; 매개 변수 형식과 정확히 일치 가까이 있어 되도록 하기만 합니다. 진행 상황에이 예의 경우 언어 변경 된 방식을 이해 하는 키입니다.  
  
2.  홍보 행사 표준 변환 보다 좋습니다. 예를 들어 승격 한 `short int` 에 `int` 변환 보다 좋지만 `int` 에 `double`합니다.  
  
3.  표준 변환 boxing 변환 보다 더 좋습니다. 예를 들어 변환는 `int` 에 `double` 은 더 잘 boxing는 `int` 에 `Object`합니다.  
  
4.  Boxing 변환을 암시적 사용자 정의 변환이 보다 더 좋습니다. 예를 들어, boxing는 `int` 에 `Object` 더 좋은의 변환 연산자를 적용 하는 것은 한 `SmallInt` 값 클래스입니다.  
  
5.  암시적 사용자 정의 변환이 전혀 변환 작업 없이 보다 더 나은있지 않습니다. 암시적 사용자 정의 변환이 (을 매개 변수 배열이 나 해당 위치에서 줄임표 형식 서명을 포함 될 수 있음을 전제로) 오류에 앞서 마지막 종료 됩니다.  
  
 그렇다면 무엇을 의미를 정확히 일치 반드시 정확 하 게 일치 하는 항목이 없음을? 예를 들어 `const char[4]` 정확히 일치 하지 않는 하나 `const char*` 또는 `String^`, 고 예에서 사용의 모호성은 두 명의 충돌 하는 정확한 일치 항목이 아직 길이가!  
  
 발생 하는 대로 정확 하 게 일치는 다양 한 trivial 변환에 포함 합니다. ISO-c + +에서 적용 될 수 있으며 여전히 정확 하 게 일치 될 수 있는 4 개의 trivial 변환이 있습니다. 3 개는 lvalue 변환 이라고 합니다. 네 번째 형식 한정 변환을 이라고 합니다. 세 가지 lvalue 변환 한정 변환이 필요로 하는 1 보다 더 정확한 일치로 처리 됩니다.  
  
 한 가지 형태의 lvalue 변환은 포인터에 네이티브 배열 변환입니다. 이 일치 하는 관련 정보는 `const char[4]` 를 `const char*`합니다. 따라서 일치 `f("abc")` 를 `f(const char*)` 정확히 일치 합니다. 언어의 이전 버전에서이 가장 일치 하는 사실입니다.  
  
 모호로 호출을 플래그를 설정 하려면 컴파일러에 대 한 따라서 하는 데는 변환은 `const char[4]` 에 `String^` 수도 간단한 변환을 통해 정확 하 게 일치 합니다. 새 언어 버전에 도입 된 변경 내용입니다. 및이 때문에 호출이 이제 플래그가 지정 모호한 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [일반적인 언어 변경 사항 (C + + /cli CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [String](../windows/string-cpp-component-extensions.md)