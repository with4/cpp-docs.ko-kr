---
title: "safe_cast (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14bcf198d527fae51a579a2aa6e072a4c57424f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="safecast-c-component-extensions"></a>safe_cast(C++ 구성 요소 확장명)
`safe_cast` 작업은 성공하는 경우 지정된 식을 지정된 형식으로 반환하고, 그렇지 않은 경우 `InvalidCastException`을 throw합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 (이 언어 기능에는 모든 런타임에 적용되는 설명이 없습니다.)  
  
### <a name="syntax"></a>구문  
  
```cpp  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>매개 변수  
  
### <a name="remarks"></a>설명  
  
## <a name="windows-runtime"></a>Windows 런타임  
 `safe_cast`에서는 지정된 식의 형식을 변경할 수 있습니다. 변수 또는 매개 변수를 특정 형식을 변환할 수 있다고 완벽하게 예상되는 경우 try-catch 블록 없이 safe_cast를 사용하면 개발 중 프로그래밍 오류를 감지할 수 있습니다. 자세한 내용은 참조 [캐스팅 (C + + /cli CX)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx)합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>매개 변수  
 *유형 id*  
 변환할 형식을 *식* 하 합니다. 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조입니다.  
  
 *식*  
 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조로 계산되는 식입니다.  
  
### <a name="remarks"></a>설명  
 `safe_cast`throw `InvalidCastException` 변환할 수 없는 경우 *식* 하 여 지정 된 형식과 *유형 id*합니다. Catch 하려면 `InvalidCastException`, 지정는 [/EH (예외 처리 모델)](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션 및 try/catch 문 사용 합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 코드 예제에서는 사용 하는 방법을 보여 줍니다. `safe_cast` Windows 런타임을 사용 합니다.  
  
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
  
```Output  
Caught expected exception: InvalidCastException  
```  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 `safe_cast`에서는 식의 형식을 변경하고 확인할 수 있는 MSIL 코드를 생성할 수 있습니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
[cli]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>매개 변수  
 *유형 id*  
 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조입니다.  
  
 *식*  
 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조로 계산되는 식입니다.  
  
### <a name="remarks"></a>설명  
 식 `safe_cast<` *유형 id*`>(`*식* `)` 피연산자 식을 형식의 개체로 변환 합니다.  
  
 컴파일러는 수락는 [static_cast](../cpp/static-cast-operator.md) 대부분의 경우에 허용 될는 `safe_cast`합니다.  그러나 `safe_cast`는 확인할 수 있는 MSIL을 생성하도록 보장되는 반면, `static_cast`는 확인할 수 없는 MSIL을 생성할 수 있습니다.  참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) 및 [Peverify.exe (PEVerify 도구)](/dotnet/framework/tools/peverify-exe-peverify-tool) 안정형 코드에 대 한 자세한 내용은 합니다.  
  
 `static_cast`와 마찬가지로 `safe_cast`는 사용자 정의 변환을 호출합니다.  
  
 캐스트에 대 한 자세한 내용은 참조 [캐스팅 연산자](../cpp/casting-operators.md)합니다.  
  
 `safe_cast`적용 되지 않습니다는 **const_cast** (캐스팅 **const**).  
  
 `safe_cast`는 cli 네임스페이스에 있습니다.  참조 [플랫폼, default 및 cli 네임 스페이스](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.  
  
 대 한 자세한 내용은 **safe_cas**t, 참조:  
  
-   [/Clr을 사용한 C 스타일 캐스트 (C + + /cli CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [방법: C++/CLI에서 safe_cast 사용](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  

### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
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
  
```Output  
Caught expected exception  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)