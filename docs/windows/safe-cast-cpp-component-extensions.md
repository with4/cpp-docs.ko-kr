---
title: "safe_cast (C++ Component Extensions) | Microsoft Docs"
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
  - "safe_cast"
  - "safe_cast_cpp"
  - "stdcli::language::safe_cast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "safe_cast keyword [C++]"
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# safe_cast (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`safe_cast` 작업은 성공하는 경우 지정된 식을 지정된 형식으로 반환하고, 그렇지 않은 경우 `InvalidCastException`을 throw합니다.  
  
## 모든 런타임  
 \(이 언어 기능에는 모든 런타임에 적용되는 설명이 없습니다.\)  
  
### 구문  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### 매개 변수  
  
### 설명  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 `safe_cast`에서는 지정된 식의 형식을 변경할 수 있습니다.  변수 또는 매개 변수를 특정 형식을 변환할 수 있다고 완벽하게 예상되는 경우 try\-catch 블록 없이 safe\_cast를 사용하면 개발 중 프로그래밍 오류를 감지할 수 있습니다.  자세한 내용은 [캐스팅\(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx)을 참조하세요.  
  
### 구문  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### 매개 변수  
 *type\-id*  
 *expression*를 변환할 형식입니다.  참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조입니다.  
  
 *expression*  
 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조로 계산되는 식입니다.  
  
### 설명  
 `safe_cast`는 *type\-id*에서 지정한 형식으로 *expression*을 변환할 수 없는 경우 `InvalidCastException`을 throw합니다.  `InvalidCastException`을 catch하려면 [\/EH\(예외 처리 모델\)](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 지정하고 try\/catch 문을 사용합니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
### 예  
 **예제**  
  
 다음 코드 예제에서는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에서 `safe_cast`를 사용하는 방법을 보여 줍니다.  
  
```cpp#  
// safe_cast_ZW.cpp  
// compile with: /ZW /EHsc  
  
using namespace default;  
using namespace Platform;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main(Array<String^>^ args) {  
   I1^ i1 = ref new X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.  
   }   
   catch(InvalidCastException^ ic) {  
     wprintf(L"Caught expected exception: %s\n", ic->Message);  
   }  
}  
```  
  
 **출력**  
  
  **Caught expected exception: InvalidCastException**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 `safe_cast`에서는 식의 형식을 변경하고 확인할 수 있는 MSIL 코드를 생성할 수 있습니다.  
  
### 구문  
  
```cpp  
  
[cli]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### 매개 변수  
 *type\-id*  
 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조입니다.  
  
 *expression*  
 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조로 계산되는 식입니다.  
  
### 설명  
 `safe_cast<` *type\-id* `>(` *expression* `)` 식은 피연산자 식을 type\-id 형식의 개체로 변환합니다.  
  
 컴파일러는 `safe_cast`를 허용할 대부분의 경우 [static\_cast](../cpp/static-cast-operator.md)를 허용합니다.  그러나 `safe_cast`는 확인할 수 있는 MSIL을 생성하도록 보장되는 반면, `static_cast`는 확인할 수 없는 MSIL을 생성할 수 있습니다.  안정형 코드에 대한 자세한 내용은 [순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md) 및 [Peverify.exe\(PEVerify 도구\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md)를 참조하세요.  
  
 `static_cast`와 마찬가지로 `safe_cast`는 사용자 정의 변환을 호출합니다.  
  
 캐스트에 대한 자세한 내용은 [캐스팅 연산자](../cpp/casting-operators.md)를 참조하세요.  
  
 `safe_cast`는 **const\_cast**\(**const**를 캐스팅\)를 적용하지 않습니다.  
  
 `safe_cast`는 cli 네임스페이스에 있습니다.  자세한 내용은 [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)를 참조하세요.  
  
 **safe\_cast**에 대한 자세한 내용은 다음을 참조하세요.  
  
-   [C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [방법: C\+\+\/CLI에서 safe\_cast 사용](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  
  
-   [방법: safe\_cast를 사용하여 다운캐스트](../misc/how-to-downcast-with-safe-cast.md)  
  
-   [방법: safe\_cast 및 제네릭 형식 사용](../misc/how-to-use-safe-cast-and-generic-types.md)  
  
-   [방법: safe\_cast 및 사용자 정의 변환 사용](../misc/how-to-use-safe-cast-and-user-defined-conversions.md)  
  
-   [방법: safe\_cast 및 Boxing 사용](../misc/how-to-use-safe-cast-and-boxing.md)  
  
-   [방법: safe\_cast 및 Unboxing 사용](../misc/how-to-use-safe-cast-and-unboxing.md)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예  
 **예제**  
  
 컴파일러에서 `static_cast`는 허용하지 않고 `safe_cast`를 허용하는 한 가지 예제는 관련 없는 인터페이스 형식 간의 캐스트에 대한 것입니다.  `safe_cast`를 사용하여 컴파일러는 변환 오류를 발생하지 않고 런타임에 검사를 수행하여 캐스트가 가능한지 확인합니다.  
  
```cpp  
// safe_cast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main() {  
   I1^ i1 = gcnew X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type  
   }   
   catch(InvalidCastException^) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 **출력**  
  
  **Caught expected exception**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)