---
title: "배열 (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- cli::array
- details::array
- lang::array
dev_langs: C++
helpviewer_keywords:
- array keyword [C++]
- declaring arrays, about declaring arrays
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 343f2369260531e828ea8db27cee5e52ea18fd31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="arrays-c-component-extensions"></a>배열(C++ 구성 요소 확장명)
`Platform::Array<T>` 형식이 C + + /CX에서는 또는 `array` 키워드 C + + /CLI로 지정 된 유형과 초기 값의 배열을 선언 합니다.  
  
## <a name="all-platforms"></a>모든 플랫폼  
 배열 선언에 닫는 꺾쇠 괄호 (>) 뒤에 개체 핸들 (^) 한정자를 사용 하 여 선언 되어야 합니다.  
 배열의 요소 수가 형식의 일부가 아닙니다. 다양 한 크기의 배열은 배열 변수를 하나 참조할 수 있습니다.  
  
 표준 c + +와 달리 첨자 포인터 산술 연산에 대 한 동의어 아니며은 누적 되지 않습니다.  
  
 배열에 대 한 자세한 내용은 다음을 참조 합니다.  
  
-   [방법: C++/CLI에서 배열 사용](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
    
-   [가변 인수 목록(...)(C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 배열은의 멤버는 `Platform` 네임 스페이스입니다. 배열은 1 차원만 될 수 있습니다.  
  
### <a name="syntax"></a>구문  
  
 구문의 첫 번째 예에서는 `ref new` 집계 키워드를 배열을 할당 합니다. 두 번째 예제에서는 로컬 배열을 선언 합니다.  
  
```  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *한정자* [선택 사항]  
 이러한 저장소 클래스 지정자 중 하나 이상이: [변경 가능한](../cpp/mutable-data-members-cpp.md), [휘발성](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [정적](../cpp/static-members-cpp.md).  
  
 `array-type`  
 형식 배열 변수입니다. 올바른 유형은 Windows 런타임 클래스 및 기본 형식, ref 클래스 및 구조체, 값 클래스 및 구조체 및 네이티브 포인터 (`type*`).  
  
 `rank`[선택 사항]  
 배열의 차원 수입니다. 1 이어야 합니다.  
  
 `identifier`  
 배열 변수의 이름입니다.  
  
 `initialization-type`  
 배열을 초기화 하는 값의 형식입니다. 일반적으로 `array-type` 및 `initialization-type` 동일한 형식이 있습니다. 그러나 형식에서 변환 하는 경우 달라질 수 있습니다 `initialization-type` 를 `array-type`-예를 들어 경우 `initialization-type` 에서 파생 된 `array-type`합니다.  
  
 `initialization-list`[선택 사항]  
 배열의 요소를 초기화 하는 중괄호에 있는 값의 쉼표로 구분 된 목록입니다. 예를 들어 경우 `rank-size-list` 된 `(3)`, 1 차원 배열의 요소 3 개를 선언 하는 `initialization list` 수 `{1,2,3}`합니다.  
  
### <a name="remarks"></a>설명  
  
 으로 참조 횟수가 계산 배열 형식이 있는지 여부를 컴파일 타임에 감지할 수 있습니다 `__is_ref_array(type)`합니다. 자세한 내용은 참조 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
### <a name="examples"></a>예제  
 다음 예제에서는 100 개의 요소가 포함 된 1 차원 배열을 만듭니다.  
  
```cpp  
// cwr_array.cpp  
// compile with: /ZW  
using namespace Platform;  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);  
   My1DArray[99] = ref new MyClass();  
}  
```  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
  
### <a name="syntax"></a>구문  
  
 사용 하 여 구문의 첫 번째 예제는 `gcnew` 키워드를 배열을 할당 합니다. 두 번째 예제에서는 로컬 배열을 선언 합니다.  
  
```  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *한정자* [선택 사항]  
 이러한 저장소 클래스 지정자 중 하나 이상이: [변경 가능한](../cpp/mutable-data-members-cpp.md), [휘발성](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [정적](../cpp/static-members-cpp.md).  
  
 `array-type`  
 형식 배열 변수입니다. 올바른 유형은 Windows 런타임 클래스 및 기본 형식, ref 클래스 및 구조체, 값 클래스 및 구조체를 네이티브 포인터 (`type*`), 및 네이티브 POD (일반 이전 데이터) 형식입니다.  
  
 `rank`[선택 사항]  
 배열의 차원 수입니다. 기본값은 1입니다. 최대값은 32입니다. 배열의 각 차원 배열입니다.  
  
 `identifier`  
 배열 변수의 이름입니다.  
  
 `initialization-type`  
 배열을 초기화 하는 값의 형식입니다. 일반적으로 `array-type` 및 `initialization-type` 동일한 형식이 있습니다. 그러나 형식에서 변환 하는 경우 달라질 수 있습니다 `initialization-type` 를 `array-type`-예를 들어 경우 `initialization-type` 에서 파생 된 `array-type`합니다.  
  
 `rank-size-list`  
 배열의 각 차원 크기의 쉼표로 구분 된 목록입니다. 또는 경우는 `initialization-list` 컴파일러가 각 차원 크기를 추론할 수, 매개 변수를 지정 하 고 `rank-size-list` 생략할 수 있습니다. 
  
 `initialization-list`[선택 사항]  
 배열의 요소를 초기화 하는 중괄호에 있는 값의 쉼표로 구분 된 목록입니다. 또는의 쉼표로 구분 된 목록에 중첩 된 *초기화 목록* 다차원 배열의 요소를에서 초기화 하는 항목입니다.  
  
 예를 들어 경우 `rank-size-list` 된 `(3)`, 1 차원 배열의 요소 3 개를 선언 하는 `initialization list` 수 `{1,2,3}`합니다. If `rank-size-list` 된 `(3,2,4)`, 첫 번째 차원, 2 개 요소, 두 번째에서 및 세 번째, 4 개의 요소가 3 개 요소의 3 차원 배열을 선언 하는 `initialization-list` 수 `{{1,2,3},{0,0},{-5,10,-21,99}}`.)  
  
### <a name="remarks"></a>설명  
  
 `array`에 [플랫폼, default 및 cli 네임 스페이스](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) 네임 스페이스입니다.  
  
 표준 c + +와 마찬가지로 배열 인덱스는 0부터 시작 하 고 대괄호 ()를 사용 하 여 배열 첨자 된 됩니다. 표준 c + +와 달리 다차원 배열 인덱스는 각 차원에 대 한 연산자를 대괄호 () 집합이 아닌 각 차원에 대 한 인덱스의 목록에 지정 됩니다. 예를 들어 *식별자*[*index1*, *index2*] 대신 *식별자*[*index1*] [ *index2*].  
  
 상속 하는 모든 관리 되는 배열 `System::Array`합니다. 속성이 나 메서드 `System::Array` 배열 변수에 곧바로 적용 될 수 있습니다.  
  
 포인터 배열을 할당 하면 요소 형식이-관리 되는 클래스에는 요소는 0으로 초기화 합니다.  
  
 배열을 할당 하면 요소 형식이 값 형식인 `V`에 대 한 기본 생성자 `V` 각 배열 요소에 적용 됩니다. 자세한 내용은 참조 [c + + 네이티브 형식에 해당 하는.NET Framework (C + + /cli CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)합니다.  
  
 컴파일 타임에 검색할 수 있습니다는 형식이 있는 공용 언어 런타임 (CLR) 배열 인지 `__is_ref_array(type)`합니다. 자세한 내용은 참조 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 다음 예제에서는 100 개의 요소를 포함 하는 1 차원 배열 및 첫 번째 차원의 요소 3 개, 두 번째, 5 개 요소 및 세 번째에서 6 개 요소를 포함 하는 3 차원 배열을 만듭니다.  
  
```cpp  
// clr_array.cpp  
// compile with: /clr  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);  
   My1DArray[99] = gcnew MyClass();  
  
   // three-dimensional array  
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);  
   My3DArray[0,0,0] = gcnew MyClass();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)