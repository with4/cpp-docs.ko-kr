---
title: __identifier (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs:
- C++
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14b68f573452d9ab8894027fd4d83c0b89f2ddf1
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018363"
---
# <a name="identifier-ccli"></a>__identifier(C++/CLI)
식별자로 Visual c + + 키워드를 사용 하도록 설정 합니다.  
  
## <a name="all-platforms"></a>모든 플랫폼  
### <a name="syntax"></a>구문  
  
```cpp  
__identifier(  
Visual_C++_keyword  
)  
```  
  
### <a name="remarks"></a>설명  
  
사용 합니다 **__identifier** 키워드 없는 식별자에 대 한 키워드는 허용 되지 않지만 스타일의 것이 좋습니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 예제에서는 클래스 이름이 **템플릿** C#에서 만들어지고 DLL로 분산 합니다. 사용 하는 Visual c + + 프로그램에는 **템플릿** 클래스를 **__identifier** 키워드는 팩트를 숨깁니다는 **템플릿** 는 표준 c + + 키워드입니다.  
  
```cs  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```cpp  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
### <a name="remarks"></a>설명  
  
 합니다 **__identifier** 키워드는 사용할 수는 `/clr` 컴파일러 옵션입니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  
  
 다음 예제에서는 클래스 이름이 **템플릿** C#에서 만들어지고 DLL로 분산 합니다. 사용 하는 Visual c + + 프로그램에는 **템플릿** 클래스를 **__identifier** 키워드는 팩트를 숨깁니다는 **템플릿** 는 표준 c + + 키워드입니다.  
  
```cs  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```cpp  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장명](../windows/component-extensions-for-runtime-platforms.md)   
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)