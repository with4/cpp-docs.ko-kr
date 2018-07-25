---
title: 재정의 (c + + 구성 요소 확장명) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6818256aafc64702e5423a5560c251e6d46750fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878881"
---
# <a name="override--c-component-extensions"></a>override(C++ 구성 요소 확장)
`override` 상황에 맞는 키워드는 형식의 멤버가 기본 클래스 또는 기본 인터페이스 멤버를 재정의함을 나타냅니다.  
  
## <a name="remarks"></a>설명  
 `override` 키워드는 네이티브 대상 (기본 컴파일러 옵션)에 대해 컴파일할 때 사용할 Windows 런타임 대상 (**/ZW** 컴파일러 옵션), 또는 공용 언어 런타임 대상을 (**/clr** 컴파일러 옵션)입니다.  
  
 재정의 지정자에 대 한 자세한 내용은 참조 [재정의 지정자는](../cpp/override-specifier.md) 및 [재정의 지정자 및 네이티브 컴파일](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)합니다.  
  
 상황에 맞는 키워드에 대 한 자세한 내용은 참조 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)합니다.  
  
## <a name="examples"></a>예제  
 **예제**  
  
 다음 코드 예제에서는 `override` 네이티브 컴파일에 사용할 수도 있습니다.  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **예제**  
  
 다음 코드 예제에서는 `override` Windows 런타임 컴파일에 사용할 수 있습니다.  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **요구 사항**  
  
 컴파일러 옵션: **/ZW**  
  
 **예제**  
  
 다음 코드 예제에서는 `override` 공용 언어 런타임 컴파일에서 사용할 수 있습니다.  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **요구 사항**  
  
 컴파일러 옵션: **/clr**  
  
## <a name="see-also"></a>참고 항목  
 [재정의 지정자](../cpp/override-specifier.md)   
 [Override 지정자](../windows/override-specifiers-cpp-component-extensions.md)