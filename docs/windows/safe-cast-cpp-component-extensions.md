---
title: safe_cast (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 94973b62b83b8b574b8747febf2204251f1642d8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017544"
---
# <a name="safecast-c-component-extensions"></a>safe_cast(C++ 구성 요소 확장명)
합니다 **safe_cast** 작업이 성공 하면 지정된 된 형식으로 지정된 된 식을 반환 합니다; 그렇지 않으면 throw `InvalidCastException`합니다.  
  
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
  
## <a name="windows-runtime"></a>Windows 런타임  
 **safe_cast** 지정 된 식의 형식을 변경할 수 있습니다. 경우에 완벽 하 게 필요한 위치 변수 또는 매개 변수를 특정 형식으로 변환할 수를 사용할 수 있습니다 **safe_cast** 없이 **try / catch** 개발 중 프로그래밍 오류를 검색 하는 블록입니다. 자세한 내용은 [캐스팅 (C + + /cli CX)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx)합니다.  
  
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
 변환할 대상 형식 *식* 하 합니다. 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조입니다.  
  
 *식*  
 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조로 계산되는 식입니다.  
  
### <a name="remarks"></a>설명  
 **safe_cast** throw `InvalidCastException` 변환할 수 없으면 *식* 하 여 지정 된 형식과 *type-id 형식의*합니다. catch 하 `InvalidCastException`를 지정 합니다 [/EH (예외 처리 모델)](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 사용 하 여를 **try/catch** 문.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
### <a name="examples"></a>예제  
  
 다음 코드 예제에 사용 하는 방법을 보여 줍니다 **safe_cast** Windows 런타임을 사용 합니다.  
  
```cpp  
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
  
```Output  
Caught expected exception: InvalidCastException  
```  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **safe_cast** 식의 형식을 변경 하 고 확인할 수 있는 MSIL 코드를 생성할 수 있습니다.  
  
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
 식을 `safe_cast<` *type-id 형식의*`>(`*식* `)` 피연산자 식을 type-id 형식의 개체로 변환 합니다.  
  
 컴파일러에서 허용 됩니다는 [static_cast](../cpp/static-cast-operator.md) 것을 허용 하는 대부분의 환경에는 **safe_cast**합니다.  그러나 **safe_cast** 안정형 MSIL을 생성 하도록 보장 됩니다 여기서는 **static_cast** 확인할 수 없는 MSIL을 생성할 수 없습니다.  참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) 하 고 [Peverify.exe (PEVerify 도구)](/dotnet/framework/tools/peverify-exe-peverify-tool) 검증할 수 있는 코드에 대 한 자세한 내용은 합니다.  
  
 와 같은 **static_cast**를 **safe_cast** 사용자 정의 변환을 호출 합니다.  
  
 캐스트에 대 한 자세한 내용은 참조 하세요. [캐스팅 연산자](../cpp/casting-operators.md)합니다.  
  
 **safe_cast** 적용 되지 않습니다는 **const_cast** (캐스팅 **const**).  
  
 **safe_cast** cli 네임 스페이스입니다.  참조 [Platform, default 및 cli 네임 스페이스](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) 자세한 내용은 합니다.  
  
 에 대 한 자세한 **safe_cast**를 참조 하세요.  
  
-   [/Clr을 사용한 C 스타일 캐스트 (C + + /cli CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [방법: C++/CLI에서 safe_cast 사용](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  

### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  
  
 하나 컴파일러 허용 하지 것입니다의 예는 **static_cast** 허용 하지만 **safe_cast** 관련 없는 인터페이스 형식 간의 캐스트입니다.  사용 하 여 **safe_cast**, 컴파일러는 변환 오류를 발급 하지 않습니다 하 고 캐스팅이 가능한 경우 런타임 시 검사를 수행 하  
  
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
  
```Output  
Caught expected exception  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)