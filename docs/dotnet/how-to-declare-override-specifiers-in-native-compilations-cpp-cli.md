---
title: "방법: 재정의 지정자 선언 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0f50e500cf25a18e86e107e22d58e6446d03379d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>방법: 네이티브 컴파일에 override 지정자 선언(C++/CLI)
[봉인 된](../windows/sealed-cpp-component-extensions.md), [추상](../windows/abstract-cpp-component-extensions.md), 및 [재정의](../windows/override-cpp-component-extensions.md) 사용 하지 않는 컴파일에 사용할 수 있는 **/ZW** 또는 [/clr](../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
> [!NOTE]
>  ISO C + + 11 표준 언어에는 [재정의](../cpp/override-specifier.md) 식별자 및 [최종](../cpp/final-specifier.md) 식별자 및 둘 다는 Visual Studio 사용에서 지원 `final` 대신 `sealed` 하려는 하는 코드에서 네이티브 전용으로 컴파일할 수 있습니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 예제에서는 `sealed` 네이티브 컴파일에 유효 합니다.  
  
### <a name="code"></a>코드  
  
```cpp  
// sealed_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
   virtual void g();  
};  
  
class X : public I1 {  
public:  
   virtual void g() sealed {}  
};  
  
class Y : public X {  
public:  
  
   // the following override generates a compiler error  
   virtual void g() {}   // C3248 X::g is sealed!  
};  
```  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 `override` 네이티브 컴파일에 유효 합니다.  
  
### <a name="code"></a>코드  
  
```cpp  
// override_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
};  
  
class X : public I1 {  
public:  
   virtual void f() override {}   // OK  
   virtual void g() override {}   // C3668 I1::g does not exist  
};  
```  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 이 예제에서는 `abstract` 네이티브 컴파일에 유효 합니다.  
  
### <a name="code"></a>코드  
  
```cpp  
// abstract_native_keyword.cpp  
class X abstract {};  
  
int main() {  
   X * MyX = new X;   // C3622 cannot instantiate abstract class  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Override 지정자](../windows/override-specifiers-cpp-component-extensions.md)