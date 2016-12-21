---
title: "Arrays (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "cli::array"
  - "details::array"
  - "lang::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array keyword [C++]"
  - "declaring arrays, about declaring arrays"
  - "arrays [C++], multidimensional"
  - "multidimensional arrays"
  - "arrays [C++]"
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
caps.latest.revision: 34
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Arrays (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]의  `Platform::Array<T>`  타입 , 또는 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]의  `array`  키워드는 지정된 형식 및 초기 값의 배열을 선언합니다.  
  
## 모든 플랫폼  
 꺾쇠 괄호 \(\>\)를 닫고난 후 핸들 개체 \(^\) 한정자를 사용하여 배열을 선언해야 합니다.  
  
 배열의 요소 개수는 형식의 일부가 아닙니다.  하나의 배열 변수는 다른 크기의 배열을 참조할 수 있습니다.  
  
 표준 C\+\+와 달리 첨자 포인터 산술 연산에 대한 동의어가 아니며 비가환적입니다.  
  
 배열에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [배열 공 분산](../misc/array-covariance.md)  
  
-   [방법: C\+\+\/CLI에서 배열 사용](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
  
-   [방법: 다차원 배열 만들기](../misc/how-to-create-multidimension-arrays.md)  
  
-   [방법: 관리되는 배열의 배열 만들기\(가변 배열\)](../misc/how-to-create-arrays-of-managed-arrays-jagged-arrays.md)  
  
-   [방법: 관리되는 배열의 Typedefs 만들기](../misc/how-to-make-typedefs-for-managed-arrays.md)  
  
-   [방법: 관리되는 배열을 템플릿 형식 매개 변수로 사용](../misc/how-to-use-managed-arrays-as-template-type-parameters.md)  
  
-   [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
-   [방법: 배열 정렬](../misc/how-to-sort-arrays.md)  
  
-   [방법: 사용자 지정 조건을 사용하여 배열 정렬](../misc/how-to-sort-arrays-using-custom-criteria.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 `Platform` 네임스페이스의 배열 및 멤버  배열은 1 차원으로만 될 수 있습니다.  
  
 **구문**  
  
 구문의 첫 번째 예제에서는  `ref new`  집계 키워드를 사용하여 배열을 할당합니다.  두 번째 예에서는 로컬 배열을 선언합니다.  
  
```  
  
        [qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = ref new [Platform::]Array< initialization-type > [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = {initialization-list [,...]}  
  
```  
  
 *qualifiers* \[선택적 요소\]  
 하나 이상의 이러한 저장소 클래스 지정자:  [변경할 수 있는](../cpp/mutable-data-members-cpp.md),  [일시적](../cpp/volatile-cpp.md),  [const](../cpp/const-cpp.md),  [extern](../cpp/using-extern-to-specify-linkage.md),  [정적](../misc/static-cpp.md).  
  
 `array-type`  
 배열 변수의 형식  올바른 유형은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 클래스 기본 형식, ref 클래스 구조체, 값 클래스 및 구조체 및 네이티브 포인터입니다 \(`type``*`\).  
  
 `rank` \[선택적 요소\]  
 배열의 차수입니다.  반드시 1이여야 합니다.  
  
 `identifier`  
 행렬 변수의 이름입니다.  
  
 `initialization-type`  
 배열을 초기화 하는 값의 형식입니다.  일반적으로  `array-type`  및  `initialization-type` 은 같은 형식입니다.  그러나  `initialization-type` 에서  `array-type` 로 변환하는 경우 형식이 달라질 수 있습니다\-예를 들어,  `initialization-type` 이  `array-type` 에서 파생된 경우.  
  
 `initialization-list` \[선택적 요소\]  
 중괄호는 배열의 요소를 초기화 하는 값의 쉼표로 구분된 목록입니다.  예를 들어, 3 요소의 1 차원 배열을 선언하는  `rank-size-list`  가  `(3)` 인 경우,   `initialization list`  는  `{1,2,3}` 가 될 수 있습니다..  
  
 **설명**  
  
 형식이  `__is_ref_array(`   `type`   `)`  참조 계산 배열인지 여부를 컴파일 타임에 감지할 수 있습니다.  자세한 내용은 [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하십시오.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
### 예제  
 다음 예제에서는 100 개의 요소가 포함된 1 차원 배열을 만듭니다.  
  
```  
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
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **구문**  
  
 구문의 첫 번째 예제에서는  `gcnew`  키워드를 사용하여 배열을 할당합니다.  두 번째 예에서는 로컬 배열을 선언합니다.  
  
```  
  
        [qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = gcnew [cli::]array< initialization-type [,rank] >(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = {initialization-list [,...]}  
  
```  
  
 *qualifiers* \[선택적 요소\]  
 하나 이상의 이러한 저장소 클래스 지정자:  [변경할 수 있는](../cpp/mutable-data-members-cpp.md),  [일시적](../cpp/volatile-cpp.md),  [const](../cpp/const-cpp.md),  [extern](../cpp/using-extern-to-specify-linkage.md),  [정적](../misc/static-cpp.md).  
  
 `array-type`  
 배열 변수의 형식  올바른 유형은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 클래스와 기본 형식, ref 클래스 및 구조체, 클래스 및 구조체, 네이티브 포인터 값 \(`type``*`\), 및 네이티브 포드 \(일반 이전 데이터\) 형식입니다.  
  
 `rank` \[선택적 요소\]  
 배열의 차수입니다.  기본값은 1입니다. 최대값은 32입니다.  배열의 각 차원은 각자의 배열입니다.  
  
 `identifier`  
 행렬 변수의 이름입니다.  
  
 `initialization-type`  
 배열을 초기화 하는 값의 형식입니다.  일반적으로  `array-type`  및  `initialization-type` 은 같은 형식입니다.  그러나  `initialization-type` 에서  `array-type` 로 변환하는 경우 형식이 달라질 수 있습니다\-예를 들어,  `initialization-type` 이  `array-type` 에서 파생된 경우.  
  
 `rank-size-list`  
 배열의 각 차원의 크기의 쉼표로 구분된 목록입니다.  또는  `initialization-list`  매개 변수를 지정하는 경우, 컴파일러가 각 차원의 크기를 추론하거나  `rank-size-list`  를 생략할 수 있습니다.  자세한 내용은 [방법: 다차원 배열 만들기](../misc/how-to-create-multidimension-arrays.md)을 참조하십시오.  
  
 `initialization-list` \[선택적 요소\]  
 중괄호는 배열의 요소를 초기화 하는 값의 쉼표로 구분된 목록입니다.  다차원 배열의 요소를 초기화하는 중첩된  *initialization\-list*  항목의 쉼표로 구분된 목록입니다.  
  
 예를 들어, 3 요소의 1 차원 배열을 선언하는  `rank-size-list`  가  `(3)` 인 경우,   `initialization list`  는  `{1,2,3}` 가 될 수 있습니다..  첫 번째 차원, 둘째, 2 요소와 4, 세 번째 요소에 있는 3 요소의 3 차원 배열을 선언 하는 `rank-size-list`  가  `(3,2,4)` 인 경우,   `initialization-list`  는  `{{1,2,3},{0,0},{-5,10,-21,99}}` 가 될 수 있습니다.\)  
  
 **설명**  
  
 `array`은 [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) 네임스페이스입니다.  
  
 표준 c\+\+와 같은 배열의 인덱스는 0부터 시작하고 배열은 대괄호 \[\]를 사용하여 아래 첨자합니다.  표준 c\+\+와는 달리 다차원 배열의 인덱스는 각 차원에 대해 대괄호\[\] 연산자 대신 각 차원에 대한 인덱스 목록에 지정됩니다.  예를 들면, *identifier*\[*index1*\]\[ *index2*\] 대신 *identifier*\[*index1*, *index2*\]입니다.  
  
 모든 관리 되는 배열은  `System::Array` 로부터 상속합니다.   `System::Array` 메서드나 속성은 배열 변수에 직접 적용할 수 있습니다.  
  
 관리되는 클래스의 요소 형식이 포인터인 배열을 할당하면 요소는 0으로 초기화합니다.  
  
 요소 형식이 값 형식  `V` 인 배열을 할당하면 , `V`  에 대한 기본 생성자는 각 배열 요소에 적용됩니다.  자세한 내용은 [C\+\+ 네이티브 형식에 해당하는 .NET Framework](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)을 참조하십시오.  
  
 컴파일 타임에 형식이  `__is_ref_array(`   `type`   `)`  공용 언어 런타임 \(CLR\) 배열 인지 여부를 검색할 수 있습니다.  자세한 내용은 [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하십시오.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 다음 예제에서는 100 개의 요소를 포함하는 1 차원 배열과 3 요소의 첫 번째 차원에서, 둘째, 5 요소 및 6 세 번째 요소에 있는 3 차원 배열을 만듭니다.  
  
```  
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
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)