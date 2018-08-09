---
title: 배열 (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- cli::array
- details::array
- lang::array
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
- declaring arrays, about declaring arrays
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58ba6d598223e63f5b28adcaedad653ffc6f386a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645570"
---
# <a name="arrays-c-component-extensions"></a>배열(C++ 구성 요소 확장명)
`Platform::Array<T>` 형식에서 C + + CX, 또는 **배열** 키워드에서 C + + CLI 초기 값을 지정 된 형식 배열을 선언 합니다.  
  
## <a name="all-platforms"></a>모든 플랫폼  
 배열 선언에 닫는 꺾쇠 괄호 (>) 후 개체 핸들 (^) 한정자를 사용 하 여 선언 되어야 합니다.  
 배열의 요소 수가 형식의 일부가 아닙니다. 다양 한 크기의 배열에 하나의 배열 변수를 참조할 수 있습니다.  
  
 표준 c + +와 달리 첨자 포인터 산술 연산에 대 한 동의어가 아닌 및은 누적 되지 않습니다.  
  
 배열에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   [방법: C++/CLI에서 배열 사용](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
    
-   [가변 인수 목록(...)(C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 배열은 멤버를 `Platform` 네임 스페이스입니다. 배열은 1 차원만 될 수 있습니다.  
  
### <a name="syntax"></a>구문  
  
 구문의 첫 번째 예제에서는 합니다 **ref n e w** 집계 키워드 배열을 할당 합니다. 두 번째 예제에는 로컬 배열을 선언합니다.  
  
```cpp  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *한정자* [선택 사항]  
 이러한 저장소 클래스 지정자 중 하나 이상이: [변경할 수 있는](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md)를 [const](../cpp/const-cpp.md)를 [extern](../cpp/using-extern-to-specify-linkage.md), [정적](../cpp/static-members-cpp.md).  
  
 *배열 형식*  
 배열 변수의 형식입니다. 올바른 유형은 Windows 런타임 클래스 및 기본 형식, ref 클래스 및 구조체, 값 클래스 및 구조체 및 네이티브 포인터 (`type*`).  
  
 *순위* [선택 사항]  
 배열의 차원 수입니다. 1 이어야 합니다.  
  
 *identifier*  
 배열 변수의 이름입니다.  
  
 *초기화 유형*  
 배열을 초기화 하는 값의 형식입니다. 일반적으로 *배열 형식* 하 고 *초기화 형식* 동일한 형식이 있습니다. 그러나 형식에서 변환 하는 경우에 다 수 *초기화 유형* 하 *배열 형식*-예를 들어 경우 *초기화 형식* 에서파생됩니다*배열 형식*합니다.  
  
 *초기화 목록* [선택 사항]  
 배열의 요소를 초기화 하는 중괄호에 있는 값의 쉼표로 구분 된 목록입니다. 예를 들어 경우 *순위 크기 목록* 되었습니다 `(3)`는 1 차원 배열의 요소 3 개를 선언 하는 *초기화 목록* 수 `{1,2,3}`입니다.  
  
### <a name="remarks"></a>설명  
  
 형식을 사용 하 여 참조 횟수가 계산 되는 배열 인지 여부를 컴파일 시간에 감지할 수 있습니다 `__is_ref_array(type)`합니다. 자세한 내용은 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
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
  
 구문의 첫 번째 예제에서는 합니다 **gcnew** 배열을 할당 하는 키워드입니다. 두 번째 예제에는 로컬 배열을 선언합니다.  
  
```cpp  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *한정자* [선택 사항]  
 이러한 저장소 클래스 지정자 중 하나 이상이: [변경할 수 있는](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md)를 [const](../cpp/const-cpp.md)를 [extern](../cpp/using-extern-to-specify-linkage.md), [정적](../cpp/static-members-cpp.md).  
  
 *배열 형식*  
 배열 변수의 형식입니다. 올바른 유형은 Windows 런타임 클래스 및 기본 형식, ref 클래스 및 구조체, 값 클래스 및 구조체를 네이티브 포인터 (`type*`), 및 네이티브 POD (일반 이전 데이터) 형식입니다.  
  
 *순위* [선택 사항]  
 배열의 차원 수입니다. 기본값은 1입니다. 최대값은 32입니다. 배열의 각 차원 배열입니다.  
  
 *identifier*  
 배열 변수의 이름입니다.  
  
 *초기화 유형*  
 배열을 초기화 하는 값의 형식입니다. 일반적으로 *배열 형식* 하 고 *초기화 형식* 동일한 형식이 있습니다. 그러나 형식에서 변환 하는 경우에 다 수 *초기화 유형* 하 *배열 형식*-예를 들어 경우 *초기화 형식* 에서파생됩니다*배열 형식*합니다.  
  
 *순위 크기 목록*  
 배열의 각 차원 크기의 쉼표로 구분 된 목록입니다. 또는 경우는 *초기화 목록* 매개 변수에 지정 된 경우 컴파일러는 각 차원 크기를 추론할 수 있습니다 하 고 *차수 크기 목록* 생략할 수 있습니다. 
  
 *초기화 목록* [선택 사항]  
 배열의 요소를 초기화 하는 중괄호에 있는 값의 쉼표로 구분 된 목록입니다. 나의 쉼표로 구분 된 목록을 중첩 *초기화 목록* 다차원 배열의 요소를 초기화 하는 항목입니다.  
  
 예를 들어 경우 *순위 크기 목록* 되었습니다 `(3)`는 1 차원 배열의 요소 3 개를 선언 하는 *초기화 목록* 수 `{1,2,3}`입니다. 하는 경우 *순위 크기 목록* 되었습니다 `(3,2,4)`, 첫 번째 차원, 2 개 요소, 두 번째에서 및 세 번째, 4 개 요소로 3 요소의 3 차원 배열을 선언 하는 *초기화 목록* 수 `{{1,2,3},{0,0},{-5,10,-21,99}}`.)  
  
### <a name="remarks"></a>설명  
  
 **배열** 에 [Platform, default 및 cli 네임 스페이스](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) 네임 스페이스입니다.  
  
 표준 c + +와 마찬가지로 배열 인덱스는 0부터 시작 합니다 하 고 대괄호 ()를 사용 하 여 배열 첨자 된 됩니다. 표준 c + +와 달리 다차원 배열의 인덱스는 각 차원에 대 한 대괄호 () 연산자 집합을 하는 대신 각 차원에 대 한 인덱스의 목록에 지정 됩니다. 예를 들어 *식별자*[*index1*하십시오 *index2*] 대신 *식별자*[*index1*] [ *index2*].  
  
 상속 하는 모든 관리 되는 배열 `System::Array`합니다. 모든 메서드 또는 속성의 `System::Array` 변수의 배열에 직접 적용할 수 있습니다.  
  
 이 포인터 배열을 할당 하면 요소 형식이-관리 되는 클래스는 요소는 0으로 초기화 합니다.  
  
 배열을 할당할 때 요소 형식이 값 형식인 `V`에 대 한 기본 생성자를 `V` 각 배열 요소에 적용 됩니다. 자세한 내용은 [c + + 네이티브 형식에.NET Framework 해당 하는 (C + + /cli CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)합니다.  
  
 형식에는 공용 언어 런타임 (CLR) 배열 인지 여부를 감지할 수 있습니다 컴파일 타임에 `__is_ref_array(type)`입니다. 자세한 내용은 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  
 다음 예제에서는 100 개의 요소를 포함 하는 1 차원 배열 및 첫 번째 차원의 3 개 요소, 5 개 요소, 두 번째에서 및 세 번째에서 6 개 요소가 있는 3 차원 배열을 만듭니다.  
  
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